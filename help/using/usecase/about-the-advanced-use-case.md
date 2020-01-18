---
title: Informazioni sul caso di utilizzo avanzato
description: Ulteriori informazioni sul viaggio caso di utilizzo avanzato
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


# Informazioni sul caso di utilizzo avanzato{#concept_vzy_ncy_w2b}

## Finalità {#purpose}

Prendiamo l&#39;esempio di un hotel di nome Marlton. Nei loro hotel, hanno posizionato i dispositivi beacon vicino a tutte le aree strategiche: hall, piani, ristorante, palestra, piscina, ecc.

>[!NOTE]
>
>In questo caso, utilizziamo Adobe Campaign Standard per inviare messaggi.

In questo caso di utilizzo, vedremo come inviare messaggi personalizzati in tempo reale ai clienti quando si trovano vicino a un beacon specifico.

Prima di tutto, vogliamo inviare un messaggio non appena una persona entra in un hotel di Marlton. Vogliamo inviare un messaggio solo se la persona non ha ricevuto alcuna comunicazione da noi entro le ultime 24 ore.

Vengono quindi verificate due condizioni:

* Se questa persona non è un membro fedeltà, gli inviamo un&#39;e-mail per partecipare all&#39;offerta di iscrizione fedeltà.
* Se questa persona è già un membro fedeltà, verifichiamo se ha una prenotazione in camera:
   * Se non lo fa, gli inviamo una notifica push con le tariffe della stanza.
   * Se lo fa, gli inviamo una notifica push di benvenuto. E se entra nel ristorante entro le prossime 6 ore, gli inviamo una notifica push con uno sconto su un pasto.

![](../assets/journeyuc2_29.png)

Per questo caso di utilizzo, sarà necessario creare due eventi (vedere [](../usecase/configuring-the-events.md)):

* L&#39;evento beacon della hall che verrà inviato al sistema quando un cliente entra nell&#39;hotel.
* Evento beacon ristorante che verrà inviato quando un cliente entra nel ristorante.

Sarà necessario configurare una connessione a due origini dati (vedere [](../usecase/configuring-the-data-sources.md)):

* L’origine dati integrata della piattaforma Experience, per recuperare le informazioni relative alle nostre due condizioni (iscrizione e data dell’ultimo contatto) e le informazioni sulla personalizzazione dei messaggi.
* Il sistema di prenotazione alberghiera, per recuperare le informazioni sullo stato della prenotazione.

## Prerequisiti {#prerequisites}

Per il nostro caso di utilizzo, abbiamo progettato tre modelli di messaggistica transazionali Adobe Campaign Standard. Stiamo utilizzando modelli di messaggistica transazionali evento. Fare riferimento a questa [pagina](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard è configurato per inviare e-mail e notifiche push.

Experience Cloud ID è utilizzato come chiave per identificare il cliente nel sistema di prenotazione alberghiera.

Gli eventi vengono inviati dal cellulare dei clienti quando vengono rilevati vicino a un beacon. Devi progettare un&#39;applicazione mobile per inviare eventi dal telefono cellulare del cliente all&#39;SDK di Mobile.

Il campo Fedeltà è un campo personalizzato ed è stato aggiunto in XDM per il nostro ID organizzazione specifico.
