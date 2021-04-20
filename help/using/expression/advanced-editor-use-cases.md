---
product: adobe campaign
solution: Journey Orchestration
title: Utilizzo dell’editor di espressioni avanzate
description: Scopri come creare espressioni avanzate
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '498'
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

Ad esempio, supponiamo che desideri indirizzare l’attività ai clienti con abbandono del carrello negli ultimi 7 giorni per inviare un messaggio quando il cliente si avvicina a un negozio, con un’offerta sugli articoli che desidera che siano in negozio.

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

```
        In( “addToCart”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        And
        Not(In( “completePurchase”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
```

Questa espressione restituisce un valore booleano.

**Ora costruiamo un&#39;espressione che controlla che il prodotto sia in magazzino**

* In Inventory, questa espressione cerca il campo quantità di un prodotto e specifica che deve essere maggiore di 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* A destra, vengono specificati i valori necessari, qui, è necessario recuperare la posizione dello store, che è mappata dalla posizione dell&#39;evento &quot;ArriveLumaStudio&quot;:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Specifica lo SKU utilizzando la funzione `first` per recuperare la più recente interazione &quot;addToCart&quot;:

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

Da qui puoi aggiungere un altro percorso nel tuo percorso per quando il prodotto non è in negozio e inviare una notifica con un’offerta di coinvolgimento. Configura i messaggi di conseguenza e utilizza i dati di personalizzazione per migliorare la destinazione del messaggio.

## Esempi di manipolazioni delle stringhe con l’editor di espressioni avanzate

**In condizioni**

Questa condizione recupera solo gli eventi recinti geografici attivati in &quot;Arlington&quot;:

```
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Spiegazione: Si tratta di un confronto rigoroso delle stringhe (distinzione tra maiuscole e minuscole), equivalente a una query in modalità semplice che utilizza `equal to` con `Is sensitive` selezionata.

La stessa query con `Is sensitive` non selezionata genera la seguente espressione in modalità avanzata:

```
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**In azioni**

La seguente espressione ti consente di definire l’ID del sistema di gestione delle relazioni con i clienti in un campo di personalizzazione delle azioni:

```
    substr(@{MobileAppLaunch
            ._myorganization
            .identification
            .crmid}, 1, 
            lastIndexOf(@{MobileAppLaunch
                        ._myorganization
                        .identification
                        .crmid}
                         }
                         ))
```

Spiegazione: In questo esempio vengono utilizzate le funzioni `substr` e `lastIndexOf` per rimuovere le parentesi graffe che racchiudono l’ID del sistema di gestione delle relazioni con i clienti passato con un evento di avvio di un’app mobile.

Per ulteriori informazioni su come utilizzare l’editor di espressioni avanzate, guarda [questo video](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
