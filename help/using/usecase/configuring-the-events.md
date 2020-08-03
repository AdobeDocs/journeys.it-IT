---
title: Configurazione degli eventi
description: Scopri come configurare gli eventi per il viaggio caso di utilizzo avanzato
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
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---


# Configurazione degli eventi {#concept_sbp_5cy_w2b}

Nel nostro scenario, dobbiamo ricevere un evento ogni volta che una persona entra nell&#39;hotel Marlton e nel ristorante. L&#39;utente **** tecnico deve configurare i due eventi che vogliamo che il sistema ascolti nel nostro viaggio.

Per ulteriori informazioni sulla configurazione dell&#39;evento, consultate [](../event/about-events.md).

1. Nel menu principale, fate clic sulla **[!UICONTROL Events]** scheda e fate clic **[!UICONTROL Add]** per creare un nuovo evento.

   ![](../assets/journeyuc1_1.png)

1. Il nome non contiene spazi o caratteri speciali: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

<!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc2_3.png" placement="break" width="800" id="image_is5_2sn_z2b"/></li-->

1. Quindi selezioniamo lo schema e definiamo il payload previsto per questo evento. Selezioniamo i campi necessari dal modello normalizzato XDM. Abbiamo bisogno dell&#39;ID Experience Cloud  per identificare la persona nel database Profilo cliente in tempo reale: &quot;endUserIDs > _experience > mcid > id&quot;.

   È inoltre necessario che il token di registrazione invii messaggi push: &quot;_experience > campaign > message > profile > pushNotificationToken > token&quot;

   Per questo evento viene generato automaticamente un ID. Questo ID è memorizzato nel **[!UICONTROL eventID]** campo (&quot;_experience > campagna > orchestrazione > eventID&quot;). Il sistema che preme l&#39;evento non deve generare un ID, ma deve utilizzare quello disponibile nell&#39;anteprima del payload. Nel nostro caso d’uso, questo ID viene usato per identificare la posizione del beacon. Ogni volta che una persona cammina vicino al beacon della hall, viene inviato un evento contenente questo ID evento specifico. Lo stesso principio si applica agli eventi del beacon ristorante. Questo consente al sistema di sapere quale beacon ha attivato l&#39;invio dell&#39;evento.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >L&#39;elenco dei campi varia da uno schema all&#39;altro. In base alla definizione dello schema, alcuni campi possono essere obbligatori e preselezionati.

1. È necessario selezionare uno spazio dei nomi. Uno spazio dei nomi è preselezionato in base alle proprietà dello schema. È possibile mantenere quello preselezionato. Per ulteriori informazioni sugli spazi dei nomi, vedere [](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Una chiave viene preselezionata in base alle proprietà dello schema e allo spazio dei nomi selezionato. Può tenerla.

   ![](../assets/journeyuc2_4bis.png)

1. Clic **[!UICONTROL Save]**.

1. Fate clic sull&#39; **[!UICONTROL View Payload]** icona per visualizzare l&#39;anteprima del payload previsto dal sistema e condividerlo con la persona responsabile dell&#39;invio dell&#39;evento.  Questo payload dovrà essere configurato nel postback della console di amministrazione di Mobile Services.

   ![](../assets/journeyuc2_5.png)

Allo stesso modo, create l’evento &quot;RestaurantBeacon&quot;. I tuoi due eventi beacon vengono creati e ora possono essere utilizzati nel nostro viaggio. È ora necessario configurare l&#39;applicazione mobile in modo che possa inviare il payload previsto all&#39;endpoint delle API di ingestione dello streaming. A questo proposito, consulta la sezione [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
