---
product: adobe campaign
solution: Journey Orchestration
title: Configurazione degli eventi
description: Scopri come configurare gli eventi per il viaggio caso di utilizzo avanzato
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 7%

---


# Configurazione degli eventi {#concept_sbp_5cy_w2b}

Nel nostro scenario, dobbiamo ricevere un evento ogni volta che una persona entra nell&#39;hotel Marlton e nel ristorante. L&#39;utente **** tecnico deve configurare i due eventi che vogliamo che il sistema ascolti nel nostro viaggio.

Per ulteriori informazioni sulla configurazione dell&#39;evento, consultate [questa pagina](../event/about-events.md).

1. In the top menu, click the **[!UICONTROL Events]** tab and click **[!UICONTROL Add]** to create a new event.

   ![](../assets/journeyuc1_1.png)

1. Il nome non contiene spazi o caratteri speciali: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

1. Quindi selezioniamo lo schema e definiamo il payload previsto per questo evento. Selezioniamo i campi necessari dal modello normalizzato XDM. Abbiamo bisogno dell&#39;ID Experience Cloud  per identificare la persona nel database Profilo cliente in tempo reale: &quot;endUserIDs > _experience > mcid > id&quot;.

   È inoltre necessario che il token di registrazione invii messaggi push: &quot;_experience > campaign > message > profile > pushNotificationToken > token&quot;

   Per questo evento viene generato automaticamente un ID. Questo ID è memorizzato nel **[!UICONTROL eventID]** campo (&quot;_experience > campagna > orchestrazione > eventID&quot;). Il sistema che preme l&#39;evento non deve generare un ID, ma deve utilizzare quello disponibile nell&#39;anteprima del payload. Nel nostro caso d’uso, questo ID viene usato per identificare la posizione del beacon. Ogni volta che una persona cammina vicino al beacon della hall, viene inviato un evento contenente questo ID evento specifico. Lo stesso principio si applica agli eventi del beacon ristorante. Questo consente al sistema di sapere quale beacon ha attivato l&#39;invio dell&#39;evento.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >L&#39;elenco dei campi varia da uno schema all&#39;altro. In base alla definizione dello schema, alcuni campi possono essere obbligatori e preselezionati.

1. È necessario selezionare uno spazio dei nomi. In base alle proprietà dello schema, viene preselezionato uno spazio dei nomi. Puoi scegliere di utilizzare quest’ultimo. For more information on namespaces, see [this page](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Una chiave viene preselezionata in base alle proprietà dello schema e allo spazio dei nomi selezionato. Può tenerla.

   ![](../assets/journeyuc2_4bis.png)

1. Fai clic su **[!UICONTROL Save]**.

1. Fate clic sull&#39; **[!UICONTROL View Payload]** icona per visualizzare l&#39;anteprima del payload previsto dal sistema e condividerlo con la persona responsabile dell&#39;invio dell&#39;evento.  Questo payload dovrà essere configurato nel postback della console di amministrazione di Mobile Services.

   ![](../assets/journeyuc2_5.png)

Allo stesso modo, create l’evento &quot;RestaurantBeacon&quot;. I tuoi due eventi beacon vengono creati e ora possono essere utilizzati nel nostro viaggio. È ora necessario configurare l&#39;applicazione mobile in modo che possa inviare il payload previsto all&#39;endpoint delle API di ingestione dello streaming. Consulta [questa pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).
