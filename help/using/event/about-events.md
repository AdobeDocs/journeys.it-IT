---
title: Informazioni sugli eventi
description: Scoprite come configurare un evento
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Informazioni sugli eventi {#concept_gfj_fqt_52b}

Un evento è collegato a una persona. Si riferisce al comportamento di una persona (ad esempio, una persona ha acquistato un prodotto, ha visitato un negozio, è uscita da un sito web, ecc.) o qualcosa che si verifica in relazione a una persona (ad esempio, una persona ha raggiunto 10 000 punti fedeltà). Questo è ciò che l&#39;orchestrazione del viaggio ascolterà nei viaggi per orchestrare le azioni migliori successive.

Questa configurazione è **obbligatoria**, in quanto l&#39;orchestrazione del percorso è progettata per ascoltare gli eventi ed è sempre eseguita da un utente **** tecnico.

La configurazione dell&#39;evento consente di definire le informazioni che l&#39;orchestrazione del viaggio riceverà come eventi. Potete utilizzare diversi eventi (in diversi passaggi di un viaggio) e diversi viaggi possono utilizzare lo stesso evento.

Se modificate un evento utilizzato in una bozza o in un viaggio live, potete solo modificare il nome, la descrizione o aggiungere campi payload. Limitiamo rigorosamente l&#39;edizione di progetti o viaggi live per evitare di interrompere i viaggi.

## Principio generale {#section_r1f_xqt_pgb}

Gli eventi sono chiamate POST API. Gli eventi vengono inviati alla piattaforma dati Adobe Experience Cloud tramite le API di ingestione dello streaming. La destinazione URL degli eventi inviati tramite le API di messaggistica transazionali è denominata &quot;ingresso&quot;. Il payload degli eventi segue la formattazione XDM.

Il payload contiene le informazioni richieste dalle API Streaming Ingestion per funzionare (nell&#39;intestazione) e le informazioni richieste dall&#39;Orchestrazione del viaggio per funzionare (l&#39;ID evento, parte del corpo del payload) e le informazioni da utilizzare nei viaggi (nel corpo, ad esempio, la quantità di un carrello abbandonato). Esistono due modalità per l’assimilazione in streaming, autenticate e non autenticate. Per informazioni dettagliate sulle API di inserimento in streaming, consultate [questo collegamento](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md).

Dopo l&#39;arrivo tramite le API Streaming Ingestion, gli eventi scorrono in un servizio interno denominato Pipeline e quindi nella Piattaforma dati. Se lo schema dell&#39;evento presenta il flag Real-time Customer Profile Service abilitato e un ID dataset che dispone anche del flag Real-time Customer Profile, questo scorre nel Real-time Customer Profile Service.

La pipeline filtra gli eventi che presentano un payload contenente gli ID evento di Orchestrazione del percorso (vedere il processo di creazione dell&#39;evento riportato di seguito) forniti dall&#39;orchestrazione del percorso e contenuti nel payload dell&#39;evento. Questi eventi vengono ascoltati dall&#39;Orchestrazione del viaggio e il percorso corrispondente viene attivato.

## Creazione di un nuovo evento {#section_tbk_5qt_pgb}

Di seguito sono riportati i passaggi principali per configurare un nuovo evento:

1. Nel menu principale, fare clic sulla **[!UICONTROL Events]**scheda. Viene visualizzato l’elenco degli eventi. Consultate[](../about/user-interface.md)per ulteriori informazioni sull&#39;interfaccia.

   ![](../assets/journey5.png)

1. Fate clic **[!UICONTROL Add]**per creare un nuovo evento. Il riquadro di configurazione dell&#39;evento si apre sul lato destro dello schermo.

   ![](../assets/journey6.png)

1. Immettete un nome per l’evento.

   >[!NOTE]
   >
   >Non utilizzate spazi o caratteri speciali. Non utilizzare più di 30 caratteri.

1. Aggiungete una descrizione all’evento. Questo passaggio è facoltativo.
1. Definire lo schema e i campi di payload: in questo punto è possibile selezionare le informazioni sull&#39;evento (in genere denominato payload) che l&#39;orchestrazione del percorso prevede di ricevere. Potrai quindi utilizzare queste informazioni nel tuo viaggio. Vedere [](../event/defining-the-payload-fields.md).
1. Il numero di viaggi che utilizzano questo evento viene visualizzato nel **[!UICONTROL Used in]**campo. Potete fare clic sull&#39;**[!UICONTROL View journeys]** icona per visualizzare l&#39;elenco dei viaggi che utilizzano questo evento.
1. Aggiungere uno spazio nomi. Questo passaggio è facoltativo ma consigliato in quanto l’aggiunta di uno spazio nomi consente di sfruttare le informazioni memorizzate nel servizio Profilo cliente in tempo reale. Definisce il tipo di chiave di cui dispone l&#39;evento. Vedere [](../event/selecting-the-namespace.md).
1. Definire la chiave: scegliete un campo dai campi di payload o definite una formula per identificare la persona associata all’evento. Se selezionate uno spazio nomi, questa chiave viene impostata automaticamente (ma può essere comunque modificata). In effetti, l&#39;orchestrazione del percorso seleziona la chiave che deve corrispondere allo spazio dei nomi (ad esempio, se si seleziona uno spazio dei nomi e-mail, verrà selezionata la chiave e-mail). Vedere [](../event/defining-the-event-key.md).
1. Aggiungi una condizione. Questo passaggio è facoltativo. Questo consente al sistema di elaborare solo gli eventi che soddisfano la condizione. La condizione può essere basata solo sulle informazioni contenute nell&#39;evento. Vedere [](../event/adding-a-condition.md).
1. Clic **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   L’evento è ora configurato e pronto per essere rilasciato in un viaggio. Per ricevere gli eventi sono necessari ulteriori passaggi di configurazione. Vedere [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
