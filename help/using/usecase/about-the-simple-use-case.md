---
product: adobe campaign
title: Informazioni sul caso d’uso semplice
description: Ulteriori informazioni sul percorso caso d’uso semplice
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: e7c3dde02837d31c5eb7d170cae7f142ce376175
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 7%

---

# Informazioni sul caso d’uso semplice{#concept_grh_vby_w2b}

## Finalità {#purpose}

Prendiamo l&#39;esempio di un marchio alberghiero chiamato Marlton. Nei loro hotel, hanno posizionato dispositivi beacon vicino a tutte le aree strategiche: hall, piani, ristorante, palestra, piscina, ecc.

In questo caso d’uso, vedremo come inviare in tempo reale un messaggio personalizzato a una persona che cammina accanto a un beacon posizionato vicino al centro benessere.

Vogliamo inviare un messaggio solo se la persona è una donna. Il messaggio deve essere ricevuto entro pochi secondi.

![](../assets/journeyuc1_16.png)

## Prerequisiti {#prerequisites}

Per il nostro caso d’uso, abbiamo progettato un modello di messaggistica transazionale e-mail in Adobe Campaign Standard. Stiamo utilizzando un modello di messaggistica transazionale di evento. Fai riferimento a questa [pagina]().

Adobe Campaign Standard è configurato per l’invio di e-mail.

Gli eventi vengono inviati dal telefono cellulare dei clienti quando vengono rilevati vicino a un beacon. Devi progettare un’app mobile per inviare eventi dal telefono cellulare del cliente all’SDK di Mobile.
