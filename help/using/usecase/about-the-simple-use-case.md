---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sul caso d’uso semplice
description: Ulteriori informazioni sul percorso caso d’uso semplice
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 11%

---


# Informazioni sul caso d’uso semplice{#concept_grh_vby_w2b}

## Finalità {#purpose}

Prendiamo l&#39;esempio di un marchio alberghiero chiamato Marlton. Nei loro hotel, hanno posizionato dispositivi beacon vicino a tutte le aree strategiche: hall, piani, ristorante, palestra, piscina, ecc.

In questo caso d’uso, vedremo come inviare in tempo reale un messaggio personalizzato a una persona che cammina accanto a un beacon posizionato vicino al centro benessere.

Vogliamo inviare un messaggio solo se la persona è una donna. Il messaggio deve essere ricevuto entro pochi secondi.

![](../assets/journeyuc1_16.png)

## Prerequisiti {#prerequisites}

Per il nostro caso d’uso, abbiamo progettato un modello di messaggistica transazionale e-mail in Adobe Campaign Standard. Stiamo utilizzando un modello di messaggistica transazionale di evento. Fai riferimento a questa [pagina](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.translate.html).

Adobe Campaign Standard è configurato per l’invio di e-mail.

Gli eventi vengono inviati dal telefono cellulare dei clienti quando vengono rilevati vicino a un beacon. Devi progettare un’app mobile per inviare eventi dal telefono cellulare del cliente all’SDK di Mobile.