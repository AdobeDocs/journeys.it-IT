---
title: Informazioni sull'orchestrazione del viaggio
description: Ulteriori informazioni sull'orchestrazione del viaggio
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 891216a489b79fe4b168ecdb6120f5d9f3e107d0

---


# Informazioni sull&#39;orchestrazione del viaggio{#concept_nd3_mqt_52b}

Creare casi di utilizzo di orchestrazione in tempo reale utilizzando i dati contestuali memorizzati in eventi o origini dati.

Journey Orchestration è un servizio di applicazione integrato con Experience Platform.

![](../assets/journeydiagram.png)

L&#39;orchestrazione del percorso consente l&#39;orchestrazione in tempo reale basata su dati contestuali derivati da eventi, informazioni provenienti da Adobe Experience Platform o dati provenienti da servizi API di terze parti. Puoi configurare un&#39;azione personalizzata se utilizzi un sistema di terze parti per l&#39;invio dei messaggi. Se disponi di Adobe Campaign Standard, sarai in grado di inviare e-mail, notifiche push e SMS utilizzando le funzionalità [di messaggistica](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)transazionali di Adobe Campaign Standard.

Nella scheda di configurazione dell’evento, un utente **** tecnico configura gli eventi previsti nei viaggi. I dati degli eventi in arrivo vengono normalizzati seguendo Adobe Experience Data Model (XDM). Gli eventi provengono dalle API Streaming Ingestion per gli eventi autenticati e non autenticati (come gli eventi SDK di Adobe Mobile).

Nella scheda di configurazione dell&#39;origine dati, un utente **** tecnico configura:

* I diversi campi esposti da Adobe Experience Platform nella finestra di progettazione dei percorsi per la creazione di condizioni e la personalizzazione.
* Le origini dati personalizzate aggiuntive utilizzate nella finestra di progettazione viaggi. Le origini dati personalizzate sono connessioni tra l&#39;Orchestrazione del percorso e sistemi o servizi di terze parti tramite API. Potete collegare un sistema di terze parti, ad esempio un sistema fidelizzato. I servizi di terze parti possono essere, ad esempio, un&#39;API meteorologica.

Con il progettista del viaggio, un utente **** aziendale può facilmente trascinare e rilasciare un evento di partecipazione, aggiungere condizioni e specificare l&#39;azione da eseguire.

Create quindi le condizioni in base a:

* time
* i dati provenienti dal payload dell&#39;evento
* informazioni provenienti da origini dati: Origine dati profilo cliente in tempo reale o origini dati personalizzate

È possibile utilizzare la condizione di divisione per indirizzare le persone nel viaggio verso direzioni diverse.

Utilizzando le attività di azione, puoi inviare un messaggio tramite un sistema di terze parti. Se disponi di Adobe Campaign Standard, invia SMS personalizzati in tempo reale, notifiche push o e-mail.

Poiché l&#39;orchestrazione del viaggio è multistep, puoi creare scenari avanzati. Ad esempio, dopo un primo evento e una prima azione, potete trascinare altri eventi. Quindi, potete aggiungere una seconda azione, inserire un&#39;attività di attesa per un certo periodo di tempo, aggiungere una condizione di divisione per spingere le persone verso due percorsi diversi e quindi inviare messaggi diversi.

>[!NOTE]
>
>Questa documentazione viene spesso aggiornata per riflettere le recenti modifiche apportate al prodotto. Tuttavia, alcune schermate possono essere leggermente diverse dall&#39;interfaccia del prodotto.
