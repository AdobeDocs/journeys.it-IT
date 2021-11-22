---
product: adobe campaign
title: Configurazione degli eventi
description: Scopri come configurare gli eventi per il percorso di casi d’uso avanzati
feature: Journeys
role: User
level: Intermediate
exl-id: 90139c72-8fae-4e6e-a79b-7c510f41fe38
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 7%

---

# Configurazione degli eventi {#concept_sbp_5cy_w2b}

Nel nostro scenario, dobbiamo ricevere un evento ogni volta che una persona entra nell&#39;hotel Marlton e nel ristorante. La **utente tecnico** deve configurare i due eventi che vogliamo che il sistema ascolti nel nostro percorso.

Per ulteriori informazioni sulla configurazione degli eventi, consulta [questa pagina](../event/about-events.md).

1. Nel menu principale, fai clic su **[!UICONTROL Events]** e fai clic su **[!UICONTROL Add]** per creare un nuovo evento.

   ![](../assets/journeyuc1_1.png)

1. Inseriamo il nome senza spazi o caratteri speciali: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

1. Quindi selezioniamo lo schema e definiamo il payload previsto per questo evento. Selezioniamo i campi necessari dal modello normalizzato XDM. È necessario l’ID Experience Cloud per identificare la persona nel database del profilo cliente in tempo reale: &quot;endUserIDs > _experience > mcid > id&quot;.

   È inoltre necessario il token di registrazione per inviare messaggi push: &quot;_experience > campagna > messaggio > profilo > pushNotificationToken > token&quot;

   Per questo evento viene generato automaticamente un ID. Questo ID è memorizzato in **[!UICONTROL eventID]** campo (&quot;_esperienza > campagna > orchestrazione > eventID&quot;). Il sistema che preme l’evento non deve generare un ID, ma deve utilizzare quello disponibile nell’anteprima del payload. Nel nostro caso d’uso, questo ID viene utilizzato per identificare la posizione del beacon. Ogni volta che una persona cammina vicino al beacon della lobby, viene inviato un evento contenente questo ID evento specifico. Lo stesso principio si applica agli eventi beacon del ristorante. Questo consente al sistema di sapere quale beacon ha attivato l’invio dell’evento.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >L’elenco dei campi varia da uno schema all’altro. In base alla definizione dello schema, alcuni campi possono essere obbligatori e preselezionati.

1. È necessario selezionare uno spazio dei nomi. In base alle proprietà dello schema, viene preselezionato uno spazio dei nomi. Puoi scegliere di utilizzare quest’ultimo. Per ulteriori informazioni sugli spazi dei nomi, consulta [questa pagina](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Viene preselezionata una chiave in base alle proprietà dello schema e allo spazio dei nomi selezionato. Puoi tenerla.

   ![](../assets/journeyuc2_4bis.png)

1. Fai clic su **[!UICONTROL Save]**.

1. Fai clic sul pulsante **[!UICONTROL View Payload]** per visualizzare in anteprima il payload previsto dal sistema e condividerlo con la persona responsabile dell’invio dell’evento.  Questo payload dovrà essere configurato nel postback della console di amministrazione di Mobile Services.

   ![](../assets/journeyuc2_5.png)

Allo stesso modo, crea l’evento &quot;RestaurantBeacon&quot;. I due eventi beacon vengono creati e possono ora essere utilizzati nel nostro percorso. Ora devi configurare l’app mobile in modo che possa inviare il payload previsto all’endpoint API Streaming Ingestion. Consulta [questa pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).
