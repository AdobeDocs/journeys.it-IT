---
product: adobe campaign
title: 'Informazioni sugli schemi ExperienceEvent per eventi di Journey Orchestration '
description: 'Scopri gli schemi ExperienceEvent per eventi Journey Orchestration '
feature: Percorsi
role: User
level: Intermediate
exl-id: ffec0d42-8632-4806-97df-da2a2372ca53
source-git-commit: 3a0fc5cd6b7bc4177ab50986b11b020a11a72c9b
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 0%

---

# Informazioni sugli schemi ExperienceEvent per gli eventi [!DNL Journey Orchestration]

[!DNL Journey Orchestration] Gli eventi sono eventi esperienza XDM che vengono inviati a Adobe Experience Platform tramite Streaming Ingestion.

Di conseguenza, un prerequisito importante per la configurazione degli eventi per [!DNL Journey Orchestration] è che tu abbia familiarità con Experience Data Model (o XDM) di Adobe Experience Platform e con le modalità di composizione degli schemi XDM Experience Event, nonché con le modalità di streaming dei dati in formato XDM in Adobe Experience Platform.

## Requisiti dello schema per gli eventi [!DNL Journey Orchestration]

Il primo passaggio nella configurazione di un evento per [!DNL Journey Orchestration] consiste nell&#39;assicurarsi di disporre di uno schema XDM definito per rappresentare l&#39;evento e di un set di dati creato per registrare le istanze dell&#39;evento in Adobe Experience Platform. Disporre di un set di dati per i tuoi eventi non è strettamente necessario, ma l’invio degli eventi a un set di dati specifico ti consentirà di mantenere la cronologia degli eventi degli utenti per riferimenti e analisi futuri, quindi è sempre una buona idea. Se non disponi già di uno schema e di un set di dati appropriati per l’evento, entrambe le attività possono essere eseguite nell’interfaccia Web di Adobe Experience Platform.

![](../assets/schema1.png)

Qualsiasi schema XDM che verrà utilizzato per eventi [!DNL Journey Orchestration] deve soddisfare i seguenti requisiti:

* Lo schema deve essere della classe ExperienceEvent XDM.

   ![](../assets/schema2.png)

* Per gli eventi generati dal sistema, lo schema deve includere il mixin eventID di Orchestration. [!DNL Journey Orchestration] utilizza questo campo per identificare gli eventi utilizzati nei percorsi.

   ![](../assets/schema3.png)

* Dichiara un campo di identità per identificare l’oggetto dell’evento. Se non viene specificata alcuna identità, è possibile utilizzare una mappa di identità. Queste operazioni non sono consigliate.

   ![](../assets/schema4.png)

* Se desideri che questi dati siano disponibili per la ricerca in un secondo momento in un Percorso, contrassegna lo schema e il set di dati per il profilo.

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* Puoi includere campi di dati per acquisire altri dati contestuali da includere con l’evento, ad esempio informazioni sull’utente, il dispositivo da cui è stato generato l’evento, la posizione o qualsiasi altra circostanza significativa correlata all’evento.

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)

## Utilizzo delle relazioni tra schemi{#leverage_schema_relationships}

Adobe Experience Platform ti consente di definire relazioni tra schemi per utilizzare un set di dati come tabella di ricerca per un altro.

Supponiamo che il modello dati del brand abbia uno schema che cattura gli acquisti. Inoltre è disponibile uno schema per il catalogo dei prodotti. Puoi acquisire l’ID prodotto nello schema di acquisto e utilizzare una relazione per cercare dettagli di prodotto più completi dal catalogo prodotti. Ciò ti consente di creare un segmento per tutti i clienti che hanno acquistato un laptop, ad esempio, senza dover elencare esplicitamente tutti gli ID dei laptop o acquisire ogni singolo dettaglio di prodotto nei sistemi transazionali.

Per definire una relazione, è necessario disporre di un campo dedicato nello schema di origine, in questo caso il campo ID prodotto nello schema di acquisto. Questo campo deve fare riferimento al campo ID prodotto nello schema di destinazione. Le tabelle di origine e di destinazione devono essere abilitate per i profili e lo schema di destinazione deve avere tale campo comune definito come identità principale.

Ecco lo schema del catalogo prodotti abilitato per il profilo con l’ID prodotto definito come identità principale.

![](../assets/schema9.png)

Ecco lo schema di acquisto con la relazione definita nel campo ID prodotto .

![](../assets/schema10.png)

>[!NOTE]
>
>Ulteriori informazioni sulle relazioni dello schema nella [documentazione di Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/configure-relationships-between-schemas.html?lang=en).

In Journey Orchestration, puoi quindi sfruttare tutti i campi delle tabelle collegate:

* durante la configurazione di un evento unitario, [Ulteriori informazioni](../event/experience-event-schema.md#unitary_event_configuration)
* quando utilizzi le condizioni in un percorso, [Ulteriori informazioni](../event/experience-event-schema.md#journey_conditions_using_event_context)
* in personalizzazione azioni personalizzata, [Ulteriori informazioni](../event/experience-event-schema.md#custom_action_personalization_with_journey_event_context)

### Configurazione di un evento unitario{#unitary_event_configuration}

I campi dello schema collegati sono disponibili nella configurazione di un evento unitario:

* quando esplori i campi dello schema evento nella schermata di configurazione dell’evento.
* quando si definisce una condizione per gli eventi generati dal sistema.

![](../assets/schema11.png)

I campi collegati non sono disponibili:

* nella formula della chiave evento
* in condizione id evento (eventi basati su regole)

Per scoprire come configurare un evento unitario, consulta questa [pagina](../event/about-creating.md).

### Condizioni di percorso che utilizzano il contesto dell’evento{#journey_conditions_using_event_context}

Puoi utilizzare i dati di una tabella di ricerca collegata a un evento utilizzato in un percorso per la creazione di condizioni (editor di espressioni).

Aggiungi una condizione in un percorso, modifica l’espressione e apri il nodo dell’evento nell’editor espressioni.

![](../assets/schema12.png)

Per informazioni su come definire le condizioni di percorso, consulta questa [pagina](../building-journeys/condition-activity.md).

### Personalizzazione delle azioni con contesto evento percorso{#custom_action_personalization_with_journey_event_context}

I campi collegati sono disponibili durante la configurazione dei parametri delle azioni di un’attività di azione del percorso.

![](../assets/schema13.png)

Per informazioni su come utilizzare le azioni personalizzate, consulta questa [pagina](../building-journeys/using-custom-actions.md).

