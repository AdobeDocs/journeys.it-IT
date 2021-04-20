---
product: adobe campaign
solution: Journey Orchestration
title: Configurazione dell’evento
description: Scopri come configurare l’evento per il percorso di casi d’uso semplici
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 8%

---


# Configurazione dell’evento{#concept_y44_hcy_w2b}

Nel nostro scenario, dobbiamo ricevere un evento ogni volta che una persona cammina vicino a un beacon posizionato accanto al centro benessere. L’ **utente tecnico** deve configurare l’evento a cui il sistema farà da listener nel nostro percorso.

Per ulteriori informazioni sulla configurazione dell&#39;evento, consulta [questa pagina](../event/about-events.md).

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Events]** e fai clic su **[!UICONTROL Add]** per creare un nuovo evento.

   ![](../assets/journeyuc1_1.png)

1. Inseriamo il nome senza spazi o caratteri speciali: &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

1. Quindi selezioniamo lo schema e definiamo il payload previsto per questo evento. Selezioniamo i campi necessari dal modello normalizzato XDM. È necessario l’ID Experience Cloud per identificare la persona nel database del profilo cliente in tempo reale: _endUserIDs > esperienza > mcid > id_. Per questo evento viene generato automaticamente un ID. Questo ID viene memorizzato nel campo **[!UICONTROL eventID]** (_esperienza > campagna > orchestrazione > eventID_). Il sistema che preme l’evento non deve generare un ID, ma deve utilizzare quello disponibile nell’anteprima del payload. Nel nostro caso d’uso, questo ID viene utilizzato per identificare la posizione del beacon. Ogni volta che una persona cammina vicino al beacon spa, viene inviato un evento contenente questo ID evento specifico. Questo consente al sistema di sapere quale beacon ha attivato l’invio dell’evento.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >L’elenco dei campi varia da uno schema all’altro. In base alla definizione dello schema, alcuni campi possono essere obbligatori e preselezionati.

1. È necessario selezionare uno spazio dei nomi. In base alle proprietà dello schema, viene preselezionato uno spazio dei nomi. Puoi scegliere di utilizzare quest’ultimo. Per ulteriori informazioni sugli spazi dei nomi, consulta [questa pagina](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. Viene preselezionata una chiave in base alle proprietà dello schema e allo spazio dei nomi selezionato. Puoi tenerla.

   ![](../assets/journeyuc1_5.png)

1. Fai clic su **[!UICONTROL Save]**.

1. Fai clic sull’icona **[!UICONTROL View Payload]** per visualizzare in anteprima il payload previsto dal sistema e condividerlo con la persona responsabile dell’invio dell’evento. Questo payload dovrà essere configurato nel postback della console di amministrazione di Mobile Services.

   ![](../assets/journeyuc1_7.png)

   L’evento è pronto per essere utilizzato nel percorso. Ora devi configurare l’app mobile in modo che possa inviare il payload previsto all’endpoint API Streaming Ingestion. Consulta [questa pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).