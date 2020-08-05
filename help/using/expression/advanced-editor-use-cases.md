---
title: Utilizzo dell’editor di espressioni avanzate
description: Scopri come creare espressioni avanzate
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: benzaama
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 2%

---


# Utilizzo dell’editor di espressioni avanzate

L&#39;editor di espressioni avanzate può essere utilizzato per creare condizioni che consentono di filtrare gli utenti durante i viaggi. Queste condizioni consentono di eseguire il targeting degli utenti in base all&#39;ora, alla data, alla posizione, alla durata o ad azioni quali l&#39;acquisto o l&#39;abbandono dei carrelli in modo che possano essere riassegnati durante il viaggio.

>[!NOTE]
>
>Gli eventi iniziano con @, origini dati con #.

## Creazione di condizioni per gli eventi di esperienza

L&#39;editor di espressioni avanzate è obbligatorio per eseguire query sulle serie temporali, ad esempio un elenco di acquisti o clic passati sui messaggi. Tali query non possono essere eseguite utilizzando l&#39;editor semplice.

Gli eventi esperienza vengono recuperati dall&#39;Adobe Experience Platform come raccolta in ordine cronologico inverso, di conseguenza:

* la prima funzione restituirà l&#39;evento più recente
* last function restituirà quella più vecchia.

Ad esempio, supponiamo di voler indirizzare i clienti con un abbandono del carrello negli ultimi 7 giorni per inviare un messaggio quando il cliente si avvicina a un negozio, con un&#39;offerta sugli articoli che voleva che fossero in negozio.

**È necessario creare le seguenti condizioni:**

Innanzitutto, eseguite il targeting dei clienti che hanno visitato lo store online ma non hanno completato l&#39;ordine negli ultimi 7 giorni.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Questa espressione cerca tutti gli eventi per l&#39;utente specificati negli ultimi 7 giorni:**

Quindi seleziona tutti gli eventi addtocart che non si sono trasformati in un completePurchase.

>[!NOTE]
>
>Per inserire rapidamente i campi nell’espressione, fate doppio clic sul campo nel pannello sinistro dell’editor.

La marca temporale specificata funge da valore data e ora, la seconda da numero di giorni.

    &quot;
    In( &quot;addToCart&quot;, #{ExperiencePlatformDataSource
    .ExperienceEventFieldGroup
    .experienceevent
    .all(
    inLastDays(currentDataPackField.timestamp, 7 ))
    .productData
    .productInteraction})
    
    AndNot(In( &quot;completePurchase&quot;, #{Experience Platform DataSource
    .ExperienceEventFieldGroup
    
    
    
    
    
    
    .experienceEvent.all(inLastDays(currentDataPackField.timestamp, 7 )).productData.productInteraction})&quot;

Questa espressione restituisce un valore booleano.

**Ora costruiamo un&#39;espressione controllando che il prodotto sia in magazzino**

* In Inventory, questa espressione cerca il campo quantità di un prodotto e specifica che deve essere maggiore di 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* A destra, i valori necessari sono specificati, qui, è necessario recuperare la posizione dello store, che è mappato dalla posizione dell&#39;evento &quot;ArriveLumaStudio&quot;:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* E specificare SKU, utilizzando la funzione `first` per recuperare l&#39;interazione &quot;addToCart&quot; più recente:

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

Da qui puoi aggiungere un altro percorso nel tuo percorso per quando il prodotto non è in negozio e inviare le notifiche con l&#39;offerta di partecipazione. Configura i messaggi di conseguenza e utilizza i dati di personalizzazione per migliorare la destinazione del messaggio.

## Esempi di manipolazione di stringhe con l&#39;editor di espressioni avanzate

**In condizioni**

Questa condizione recupera solo gli eventi geofence attivati in &quot;Arlington&quot;:

    &quot;
    @{GeofenceEntry
    .placeContext
    .POIinteractive
    .POIDetail
    .name} == &quot;Arlington&quot;
    &quot;

Spiegazione: Si tratta di un confronto stretto tra stringhe (con distinzione tra maiuscole e minuscole), che equivale a una query in modalità semplice utilizzata `equal to` con `Is sensitive` selezionata.

La stessa query con `Is sensitive` non selezionato genererà la seguente espressione in modalità avanzata:

    &quot;
    EqualIgnoreCase(@{GeofenceEntry
    .placeContext
    .POIinteractive
    .POIDetail
    .name}, &quot;Arlington&quot;)
    
    &quot;

**In azioni**

La seguente espressione consente di definire l&#39;ID CRM in un campo di personalizzazione azione:

    &quot;
    substr(@{MobileAppLaunch
    ._myorganizzazione
    .Identification
    .crmid}, 1,
    lastIndexOf(@{MobileAppLaunch
    ._myorganizzazione
    .Identification
    .crmid}
    }
    )
    
    &quot;

Spiegazione: In questo esempio vengono utilizzate `substr` e `lastIndexOf` funzioni per rimuovere le parentesi graffe che contengono l&#39;ID CRM passato con un evento di avvio dell&#39;app mobile.

Per ulteriori informazioni sull’utilizzo dell’editor di espressioni avanzate, guardate [questo video](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
