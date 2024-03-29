---
product: adobe campaign
title: Configurazione dell’evento
description: Scopri come configurare l’evento per il caso d’uso semplice del percorso
feature: Journeys
role: User
level: Intermediate
exl-id: 7423f4eb-005d-43a5-a403-97bee1e8d480
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 8%

---

# Configurazione dell’evento{#concept_y44_hcy_w2b}

Nel nostro scenario, dobbiamo ricevere un evento ogni volta che una persona cammina vicino a un beacon posizionato accanto al centro benessere. Il **utente tecnico** deve configurare l&#39;evento a cui il percorso farà da listener.

Per ulteriori informazioni sulla configurazione dell’evento, consulta [questa pagina](../event/about-events.md).

1. Nel menu principale, fai clic su **[!UICONTROL Events]** e fai clic su **[!UICONTROL Add]** per creare un nuovo evento.

   ![](../assets/journeyuc1_1.png)

1. Immettiamo il nome senza spazi o caratteri speciali: &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

1. Quindi selezioniamo lo schema e definiamo il payload previsto per questo evento. Selezioniamo i campi necessari dal modello normalizzato XDM. Per identificare la persona nel database dei profili cliente in tempo reale, è necessario disporre dell’ID Experience Cloud: _endUserIDs > esperienza > mcid > id_. Per questo evento viene generato automaticamente un ID. Questo ID è memorizzato in **[!UICONTROL eventID]** campo (_esperienza > campagna > orchestrazione > eventID_). Il sistema che trasmette l’evento non deve generare un ID, deve utilizzare quello disponibile nell’anteprima del payload. Nel nostro caso di utilizzo, questo ID viene utilizzato per identificare la posizione del beacon. Ogni volta che una persona cammina vicino al beacon spa, viene inviato un evento contenente questo ID evento specifico. Questo consente al sistema di sapere quale beacon ha attivato l’invio dell’evento.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >L’elenco dei campi varia da uno schema all’altro. In base alla definizione dello schema, alcuni campi possono essere obbligatori e preselezionati.

1. È necessario selezionare uno spazio dei nomi. In base alle proprietà dello schema, viene preselezionato uno spazio dei nomi. Puoi scegliere di utilizzare quest’ultimo. Per ulteriori informazioni sugli spazi dei nomi, consulta [questa pagina](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. Una chiave viene preselezionata in base alle proprietà dello schema e allo spazio dei nomi selezionato. Puoi tenerla.

   ![](../assets/journeyuc1_5.png)

1. Fai clic su **[!UICONTROL Save]**.

1. Fai clic su **[!UICONTROL View Payload]** per visualizzare in anteprima il payload previsto dal sistema e condividerlo con la persona responsabile dell’invio dell’evento. Questo payload dovrà essere configurato nel postback della console di amministrazione di Mobile Services.

   ![](../assets/journeyuc1_7.png)

   L’evento è pronto per essere utilizzato nel tuo percorso. Ora devi configurare l’app mobile in modo che possa inviare il payload previsto all’endpoint delle API Streaming Ingestion. Consulta [questa pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).
