---
title: Informazioni sul caso di utilizzo semplice
description: Ulteriori informazioni sul percorso caso di utilizzo semplice
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
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab

---


# Informazioni sul caso di utilizzo semplice{#concept_grh_vby_w2b}

## Finalità {#purpose}

Prendiamo l&#39;esempio di un hotel di nome Marlton. Nei loro hotel, hanno posizionato i dispositivi beacon vicino a tutte le aree strategiche: hall, piani, ristorante, palestra, piscina, ecc.

In questo caso d&#39;uso, vedremo come inviare un messaggio personalizzato in tempo reale a una persona che cammina accanto a un beacon posizionato vicino al centro benessere.

Vogliamo mandare un messaggio solo se la persona è una donna. Il messaggio deve essere ricevuto entro pochi secondi.

![](../assets/journeyuc1_16.png)

## Prerequisiti {#prerequisites}

Per il nostro caso d&#39;uso, abbiamo progettato un modello di messaggio per le transazioni e-mail in Adobe Campaign Standard. Stiamo utilizzando un modello di messaggi transazionali evento. Fare riferimento a questa [pagina](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard è configurato per l&#39;invio di e-mail.

Gli eventi vengono inviati dal cellulare dei clienti quando vengono rilevati vicino a un beacon. Devi progettare un&#39;applicazione mobile per inviare eventi dal telefono cellulare del cliente all&#39;SDK di Mobile.