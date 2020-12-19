---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sul caso d’uso semplice
description: Ulteriori informazioni sul percorso caso di utilizzo semplice
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Informazioni sul caso d’uso semplice{#concept_grh_vby_w2b}

## Finalità {#purpose}

Prendiamo l&#39;esempio di un hotel di nome Marlton. Nei loro hotel, hanno posizionato i dispositivi beacon vicino a tutte le aree strategiche: hall, piani, ristorante, palestra, piscina, ecc.

In questo caso d&#39;uso, vedremo come inviare un messaggio personalizzato in tempo reale a una persona che cammina accanto a un beacon posizionato vicino al centro benessere.

Vogliamo mandare un messaggio solo se la persona è una donna. Il messaggio deve essere ricevuto entro pochi secondi.

![](../assets/journeyuc1_16.png)

## Prerequisiti {#prerequisites}

Per il nostro caso d&#39;uso, abbiamo progettato un modello di messaggistica transazionale e-mail in  Adobe Campaign Standard. Stiamo utilizzando un modello di messaggi transazionali evento. Fare riferimento a questa [pagina](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.translate.html).

 Adobe Campaign Standard è configurato per l&#39;invio di e-mail.

Gli eventi vengono inviati dal cellulare dei clienti quando vengono rilevati vicino a un beacon. Devi progettare un&#39;applicazione mobile per inviare eventi dal telefono cellulare del cliente all&#39;SDK di Mobile.