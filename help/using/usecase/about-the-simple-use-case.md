---
product: adobe campaign
title: Informazioni sul caso d’uso semplice
description: Scopri di più sul caso d’uso semplice del percorso
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 6%

---

# Informazioni sul caso d’uso semplice{#concept_grh_vby_w2b}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


## Scopo {#purpose}

Prendiamo l&#39;esempio di un marchio di hotel chiamato Marlton. Nei loro hotel, hanno posizionato dispositivi beacon vicino a tutte le aree strategiche: hall, piani, ristorante, palestra, piscina, ecc.

In questo caso d’uso, vedremo come inviare un messaggio personalizzato in tempo reale a una persona che cammina accanto a un beacon posizionato vicino all’applicazione a pagina singola.

Vogliamo inviare un messaggio solo se la persona è una donna. Il messaggio deve essere ricevuto entro pochi secondi.

![](../assets/journeyuc1_16.png)

## Prerequisiti {#prerequisites}

Per il nostro caso d’uso, abbiamo progettato un modello di messaggistica transazionale e-mail in Adobe Campaign Standard. Stiamo utilizzando un modello per la messaggistica transazionale di eventi. Fai riferimento a questa [pagina](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=it).

Adobe Campaign Standard è configurato per l’invio di e-mail.

Gli eventi vengono inviati dal telefono cellulare dei clienti quando vengono rilevati vicino a un beacon. È necessario progettare un’app mobile per inviare eventi dal telefono cellulare del cliente al SDK mobile.
