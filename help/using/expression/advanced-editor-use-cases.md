---
product: adobe campaign
title: Utilizzo dell’editor di espressioni avanzate
description: Scopri come creare espressioni avanzate
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# Esempi di espressione avanzati

L’editor di espressioni avanzate può essere utilizzato per creare condizioni che consentono di filtrare gli utenti nei percorsi. Queste condizioni ti consentono di eseguire il targeting degli utenti in base a ora, data, posizione, durata o azioni quali l’acquisto o l’abbandono dei carrelli in modo che possano essere reindirizzati nel percorso.

>[!NOTE]
>
>Gli eventi iniziano con @, origini dati con #.

## Creazione di condizioni sugli eventi di esperienza

L’editor di espressioni avanzate è obbligatorio per eseguire query su serie temporali come un elenco di acquisti o clic passati sui messaggi. Tali query non possono essere eseguite utilizzando il semplice editor.

Gli eventi di esperienza vengono recuperati da Adobe Experience Platform come raccolta in ordine cronologico inverso, quindi:

* la prima funzione restituirà l’evento più recente
* l&#39;ultima funzione restituirà quella più vecchia.

Ad esempio, supponiamo che desideri indirizzare l’attività ai clienti con un abbandono del carrello negli ultimi 7 giorni per inviare un messaggio quando il cliente si avvicina a un negozio, con un’offerta sugli articoli che desiderano che siano in negozio.

**Devi creare le seguenti condizioni:**

Innanzitutto, rivolgiti ai clienti che hanno visitato il negozio online ma non hanno finalizzato l&#39;ordine negli ultimi 7 giorni.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Questa espressione cerca tutti gli eventi per l&#39;utente specificato negli ultimi 7 giorni:**

Quindi seleziona tutti gli eventi addtocart che non si sono trasformati in un completePurchase.

>[!NOTE]
>
>Per inserire rapidamente i campi nell’espressione, fai doppio clic sul campo nel pannello a sinistra dell’editor.

La marca temporale specificata agisce come valore dell&#39;ora della data, la seconda come numero di giorni.

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

Questa espressione restituisce un valore booleano.

**Ora costruiamo un&#39;espressione che controlla che il prodotto sia in magazzino**

* In Inventory, questa espressione cerca il campo quantità di un prodotto e specifica che deve essere maggiore di 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* A destra, i valori necessari sono specificati, qui, dobbiamo recuperare la posizione dello store, che è mappata dalla posizione dell&#39;evento &quot;ArriveLumaStudio&quot;:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* E specificare SKU, utilizzando la funzione `first` per recuperare la più recente interazione &quot;addToCart&quot;:

   ```json
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == "addToCart"
                       )
                       .SKU}
   ```

Da qui puoi aggiungere un altro percorso nel tuo percorso per quando il prodotto non è in negozio e inviare una notifica con un’offerta di coinvolgimento. Configura i messaggi di conseguenza e utilizza i dati di personalizzazione per migliorare la destinazione del messaggio.

## Esempi di manipolazioni delle stringhe con l’editor di espressioni avanzate

**In condizioni**

Questa condizione recupera solo gli eventi recinti geografici attivati in &quot;Arlington&quot;:

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Spiegazione: Si tratta di un confronto rigoroso delle stringhe (distinzione tra maiuscole e minuscole), equivalente a una query in modalità semplice che utilizza `equal to` con `Is sensitive` controllati.

La stessa query con `Is sensitive` deselezionata genera la seguente espressione in modalità avanzata:

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**In azioni**

La seguente espressione ti consente di definire l’ID del sistema di gestione delle relazioni con i clienti in un campo di personalizzazione delle azioni:

```json
substr(
   @{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

Spiegazione: Questo esempio utilizza `substr` e `lastIndexOf` funzioni per rimuovere le parentesi graffe che racchiudono l’ID CRM passato con un evento di avvio dell’app mobile.

Per ulteriori informazioni su come utilizzare l’editor di espressioni avanzate, consulta [questo video](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
