---
product: adobe campaign
title: Informazioni sul caso d’uso avanzato
description: Ulteriori informazioni sul caso d’uso avanzato percorso
feature: Journeys
role: User
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 4%

---

# Informazioni sul caso d’uso avanzato{#concept_vzy_ncy_w2b}

## Finalità {#purpose}

Prendiamo l&#39;esempio di un marchio alberghiero chiamato Marlton. Nei loro hotel, hanno posizionato dispositivi beacon vicino a tutte le aree strategiche: hall, piani, ristorante, palestra, piscina, ecc.

>[!NOTE]
>
>In questo caso d’uso, utilizziamo Adobe Campaign Standard per inviare messaggi.

In questo caso d’uso, vedremo come inviare messaggi personalizzati in tempo reale ai clienti quando si trovano vicino a un beacon specifico.

Prima di tutto, vogliamo inviare un messaggio non appena una persona entra in un hotel a Marlton. Vogliamo inviare un messaggio solo se la persona non ha ricevuto alcuna comunicazione da noi entro le ultime 24 ore.

Poi controlliamo due condizioni:

* Se questa persona non è un membro fedeltà, gli inviamo un’e-mail per partecipare all’offerta di iscrizione fedeltà.
* Se questa persona è già un membro fedeltà, verifichiamo se ha una prenotazione in camera:
   * Se non lo fa, gli inviamo una notifica push con le tariffe della stanza.
   * Se lo fa, inviamo loro una notifica push di benvenuto. E se entra nel ristorante entro le prossime 6 ore, gli inviamo una notifica push con uno sconto su un pasto.

![](../assets/journeyuc2_29.png)

Per questo caso d’uso, dovremo creare due eventi (vedi [questa pagina](../usecase/configuring-the-events.md)):

* L&#39;evento beacon della lobby che verrà inviato al sistema quando un cliente entra nell&#39;hotel.
* Evento beacon del ristorante che verrà inviato quando un cliente entra nel ristorante.

Sarà necessario configurare una connessione a due origini dati (vedi [questa pagina](../usecase/configuring-the-data-sources.md)):

* L’origine dati integrata di Adobe Experience Platform, per recuperare le informazioni per le nostre due condizioni (iscrizione fedeltà e data dell’ultimo contatto) e le informazioni sulla personalizzazione dei messaggi.
* Il sistema di prenotazione alberghiera, per recuperare le informazioni sullo stato della prenotazione.

## Prerequisiti {#prerequisites}

Per il nostro caso d’uso, abbiamo progettato tre modelli di messaggistica transazionale Adobe Campaign Standard. Stiamo utilizzando modelli di messaggistica transazionale di eventi. Fai riferimento a questo [page](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=it).

Adobe Campaign Standard è configurato per l’invio di e-mail e notifiche push.

L&#39;ID Experience Cloud viene utilizzato come chiave per identificare il cliente nel sistema di prenotazione alberghiera.

Gli eventi vengono inviati dal telefono cellulare dei clienti quando vengono rilevati vicino a un beacon. Devi progettare un’app mobile per inviare eventi dal telefono cellulare del cliente all’SDK di Mobile.

Il campo Membro fedeltà è un campo personalizzato ed è stato aggiunto in XDM per il nostro ID organizzazione specifico.
