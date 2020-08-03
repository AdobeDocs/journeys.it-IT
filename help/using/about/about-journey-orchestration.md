---
title: Informazioni su Journey Orchestration
description: Ulteriori informazioni su Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 19%

---


# Informazioni [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}

Crea casi di utilizzo di orchestrazione in tempo reale sulla base dei dati contestuali memorizzati negli eventi o nelle origini dati.

[!DNL Journey Orchestration] è un servizio di applicazione integrato con il Adobe Experience Platform .

![](../assets/journeydiagram.png)

[!DNL Journey Orchestration] consente l’orchestrazione in tempo reale basata su dati contestuali derivati dagli eventi, su informazioni provenienti da Adobe Experience Platform oppure su dati di servizi API di terze parti. Puoi configurare un&#39;azione personalizzata se utilizzi un sistema di terze parti per l&#39;invio dei messaggi. Se si dispone  Adobe Campaign Standard, sarà possibile inviare e-mail, notifiche push e SMS utilizzando le  funzionalità [di messaggistica](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.translate.html)transazionali  Adobe Campaign Standard.

Nella scheda di configurazione dell’evento, un utente **** tecnico configura gli eventi previsti nei viaggi. I dati degli eventi in arrivo vengono normalizzati seguendo Adobe Experience Data Model (XDM). Gli eventi provengono dalle API Streaming Ingestion per gli eventi autenticati e non autenticati (come  eventi SDK Mobile di Adobe).

Nella scheda di configurazione dell&#39;origine dati, un utente **** tecnico configura:

* I diversi campi esposti dal Adobe Experience Platform  nel progettista di viaggi per scopi di creazione di condizioni e personalizzazione.
* Le origini dati personalizzate aggiuntive utilizzate nella finestra di progettazione viaggi. Le origini dati personalizzate sono connessioni tra sistemi o servizi di [!DNL Journey Orchestration] terze parti tramite API. Potete collegare un sistema di terze parti, ad esempio un sistema fidelizzato. I servizi di terze parti possono essere, ad esempio, un&#39;API meteorologica.

Con il progettista del viaggio, un utente **** aziendale può facilmente trascinare e rilasciare un evento di partecipazione, aggiungere condizioni e specificare l&#39;azione da eseguire.

Create quindi le condizioni in base a:

* time
* i dati provenienti dal payload dell&#39;evento
* informazioni provenienti da origini dati: Origine dati profilo cliente in tempo reale o origini dati personalizzate

È possibile utilizzare la condizione di divisione per indirizzare le persone nel viaggio verso direzioni diverse.

Utilizzando le attività di azione, puoi inviare un messaggio tramite un sistema di terze parti. Se hai  Adobe Campaign Standard, invia SMS personalizzati in tempo reale, notifiche push o e-mail.

Come [!DNL Journey Orchestration] accade per più passaggi, potete creare scenari avanzati. Ad esempio, dopo un primo evento e una prima azione, potete trascinare altri eventi. Quindi, potete aggiungere una seconda azione, inserire un&#39;attività di attesa per un certo periodo di tempo, aggiungere una condizione di divisione per spingere le persone verso due percorsi diversi e quindi inviare messaggi diversi.

>[!NOTE]
>
>Questa documentazione viene spesso aggiornata per riflettere le recenti modifiche apportate al prodotto. Tuttavia, alcune schermate possono risultare leggermente diverse dall’interfaccia del prodotto.
