---
product: adobe campaign
title: Informazioni su Journey Orchestration
description: Ulteriori informazioni su Journey Orchestration
feature: Journeys
role: Business Practitioner
level: Beginner
exl-id: 430bac3a-06da-45a8-af90-1dcd1504d532
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 100%

---

# Informazioni su [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}

Crea casi di utilizzo di orchestrazione in tempo reale sulla base dei dati contestuali memorizzati negli eventi o nelle origini dati.

[!DNL Journey Orchestration] è un servizio applicativo integrato con Adobe Experience Platform.

![](../assets/journeydiagram.png)

[!DNL Journey Orchestration] consente l’orchestrazione in tempo reale basata su dati contestuali derivati dagli eventi, su informazioni provenienti da Adobe Experience Platform oppure su dati di servizi API di terze parti. Puoi configurare un’azione personalizzata se utilizzi un sistema di terze parti per l’invio dei messaggi. Se disponi di Adobe Campaign Standard, potrai eseguire l’invio di e-mail, notifiche push e SMS tramite le [funzionalità di messaggistica transazionale](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.translate.html) di Adobe Campaign Standard.

Nella scheda di configurazione dell’evento, **un utente tecnico** configura gli eventi previsti nei percorsi. I dati degli eventi in arrivo vengono normalizzati seguendo Adobe Experience Data Model (XDM). Gli eventi provengono dalle API Streaming Ingestion per gli eventi autenticati e non autenticati, ad esempio gli eventi SDK di Adobe Mobile.

Nella scheda di configurazione dell’origine dati, un **utente tecnico** configura:

* I diversi campi esposti da Adobe Experience Platform nel designer del percorso a scopo di creazione di condizioni e di personalizzazione.
* Le origini dati personalizzate aggiuntive utilizzate nel designer del percorso. Le origini dati personalizzate rappresentano le connessioni tra [!DNL Journey Orchestration] e i sistemi o i servizi di terze parti tramite API. Puoi eseguire il collegamento di un sistema di terze parti, ad esempio un sistema di fidelizzazione. I servizi di terze parti possono essere, ad esempio, un’API per il meteo.

Grazie al designer del percorso, un **utente aziendale** può trascinare facilmente un evento di partecipazione, aggiungere condizioni e specificare l’azione da eseguire.

A quel punto potrai creare le condizioni in base a:

* orario
* dati provenienti dal payload dell’evento
* informazioni provenienti dalle origini dati, come Profilo del cliente in tempo reale o altre origini dati personalizzate

Puoi utilizzare la condizione di suddivisione per inviare in direzioni diverse le persone presenti nel percorso.

Utilizzando le attività di azione, puoi inviare un messaggio tramite un sistema di terze parti. Se possiedi Adobe Campaign Standard, potrai inviare SMS personalizzati, notifiche push o e-mail in tempo reale.

Dato che [!DNL Journey Orchestration] prevede più passaggi, puoi creare scenari avanzati. Ad esempio, dopo un primo evento e una prima azione, puoi trascinare altri eventi. Quindi, puoi aggiungere una seconda azione, inserire un’attività Attendi per un certo periodo di tempo, inserire una condizione di suddivisione per spingere le persone verso due percorsi diversi e infine inviare messaggi differenti.

>[!NOTE]
>
>Questa documentazione viene spesso aggiornata per riflettere le recenti modifiche apportate al prodotto. Tuttavia, alcune schermate possono risultare leggermente diverse dall’interfaccia del prodotto.
