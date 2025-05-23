---
product: adobe campaign
title: Utilizzo dell’editor di espressioni avanzate
description: Scopri come creare espressioni avanzate
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---

# Esempi di espressioni avanzate


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home) per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


L’editor di espressioni avanzate può essere utilizzato per creare condizioni che consentono di filtrare gli utenti nei percorsi. Queste condizioni ti consentono di eseguire il targeting degli utenti in base a ora, data, posizione, durata o azioni quali l’acquisto o l’abbandono dei carrelli, in modo che possano essere indirizzati nuovamente al percorso.

>[!NOTE]
>
>Gli eventi iniziano con @, le origini dati con #.

## Creazione delle condizioni per gli eventi esperienza

L’editor di espressioni avanzate è obbligatorio per eseguire query su serie temporali come un elenco di acquisti o clic sui messaggi passati. Tali query non possono essere eseguite utilizzando l’editor semplice.

Gli eventi di esperienza vengono recuperati da Adobe Experience Platform come raccolta in ordine cronologico inverso, quindi:

* la prima funzione restituirà l’evento più recente
* last function restituirà quella più vecchia.

Ad esempio, supponiamo che tu voglia indirizzare i clienti con un abbandono del carrello negli ultimi 7 giorni per inviare un messaggio quando il cliente si avvicina a un negozio, con un’offerta sugli articoli che voleva fossero in negozio.

**È necessario creare le seguenti condizioni:**

Innanzitutto, rivolgiti ai clienti che hanno navigato nel negozio online ma non hanno finalizzato l’ordine negli ultimi 7 giorni.

<!--**This expression looks for a specified value in a string value:**

`In ("addToCart", #{field reference from experience event})`-->

**L&#39;espressione cerca tutti gli eventi per l&#39;utente specificato negli ultimi 7 giorni:**

Quindi seleziona tutti gli eventi addtocart che non si sono trasformati in un completePurchase.

>[!NOTE]
>
>Per inserire rapidamente i campi nell’espressione, fai doppio clic sul campo nel pannello a sinistra dell’editor.

La marca temporale specificata funge da valore data/ora, la seconda da numero di giorni.

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

**Ora creiamo un&#39;espressione per verificare che il prodotto sia disponibile**

* In Inventory, questa espressione cerca il campo quantità di un prodotto e specifica che deve essere maggiore di 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* A destra, vengono specificati i valori necessari. In questo caso, è necessario recuperare la posizione del negozio, mappata dalla posizione dell’evento &quot;ArriveLumaStudio&quot;:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* E specificare SKU, utilizzando la funzione `first` per recuperare l&#39;interazione &quot;addToCart&quot; più recente:

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

Da lì puoi aggiungere un altro percorso nel percorso per quando il prodotto non è in negozio e inviare una notifica con l’offerta di coinvolgimento. Configura i messaggi di conseguenza e utilizza i dati di personalizzazione per migliorare il target del messaggio.

## Esempi di manipolazioni delle stringhe con l’editor di espressioni avanzate

**In condizioni**

Questa condizione recupera solo gli eventi del recinto geografico attivati in &quot;Arlington&quot;:

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Spiegazione: Si tratta di un confronto stringhe rigoroso (distinzione maiuscole/minuscole), equivalente a una query in modalità semplice che utilizza `equal to` con `Is sensitive` selezionato.

La stessa query con `Is sensitive` deselezionato genererà la seguente espressione in modalità avanzata:

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**In azioni**

L’espressione seguente ti consente di definire l’ID del sistema di gestione delle relazioni con i clienti in un campo di personalizzazione delle azioni:

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

Spiegazione: In questo esempio vengono utilizzate le funzioni `substr` e `lastIndexOf` per rimuovere le parentesi graffe che racchiudono l&#39;ID CRM passato con un evento di avvio dell&#39;app mobile.

Per ulteriori informazioni su come utilizzare l&#39;editor di espressioni avanzate, guarda [questo video](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html?lang=it).
