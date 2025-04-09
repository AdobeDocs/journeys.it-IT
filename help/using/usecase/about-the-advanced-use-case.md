---
product: adobe campaign
title: Informazioni sul caso d’uso avanzato
description: Scopri di più sul caso d’uso avanzato del percorso
feature: Journeys
role: User
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 2%

---

# Informazioni sul caso d’uso avanzato{#concept_vzy_ncy_w2b}


>[!CAUTION]
>
>**Cerchi Adobe Systems Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home) per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy sostituiti da Journey Optimizer. Contatta il tuo team account se hai domande sulle accesso a Journey Orchestration o Journey Optimizer._


## Scopo {#purpose}

Prendiamo l&#39;esempio di un hotel marchio chiamato Marlton. Nei loro hotel, hanno posizionato dispositivi beacon vicino a tutte le aree strategiche: hall, piani, ristorante, palestra, piscina, ecc.

>[!NOTE]
>
>In questo caso d&#39;uso, utilizziamo Adobe Campaign Standard per inviare messaggi.

In questo caso d&#39;uso, vedremo come inviare messaggi personalizzati in tempo reale ai clienti quando camminano vicino a un beacon specifico.

Prima di tutto, vogliamo inviare un messaggio non appena una persona entra in un hotel Marlton. Vogliamo inviare un messaggio solo se la persona non ha ricevuto alcuna comunicazione da noi nelle ultime 24 ore.

Verifichiamo quindi due condizioni:

* Se questa persona non è un membro fedeltà, gli inviamo un’e-mail per partecipare all’offerta di iscrizione fedeltà.
* Se questa persona è già un membro fedeltà, controlliamo se ha una prenotazione di camera:
   * Se non lo fa, inviamo loro una spinta notifica con le tariffe delle camere.
   * Se lo fa, inviamo loro una gradita spinta notifica. E se entra nel ristorante entro le prossime 6 ore, inviamo loro una spinta notifica con uno sconto su un pasto.

![](../assets/journeyuc2_29.png)

Per questo caso d&#39;uso, dovremo creare due eventi (vedi [questa pagina](../usecase/configuring-the-events.md)):

* Evento beacon della hall che verrà inviato al sistema quando un cliente entra nell&#39;hotel.
* Evento beacon ristorante che verrà inviato quando un cliente entra nel ristorante.

Sarà necessario configurare una connessione a due origini dati (vedere [questa pagina](../usecase/configuring-the-data-sources.md)):

* L’origine dati integrata di Adobe Experience Platform, per recuperare le informazioni relative alle due condizioni (iscrizione fedeltà e data dell’ultimo contatto) e le informazioni sulla personalizzazione del messaggio.
* Il sistema di prenotazione dell’hotel, per recuperare le informazioni sullo stato della prenotazione.

## Prerequisiti {#prerequisites}

Per il nostro caso d&#39;uso, abbiamo progettato tre Adobe Campaign Standard modelli di messaggistica transazionali. Stiamo usando modelli di messaggistica transazionali degli eventi. Fare riferimento a questa [pagina](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=it).

Adobe Campaign Standard è configurato per inviare e-mail e notifiche push.

L&#39;ID Experience Cloud viene utilizzato come chiave per identificare il cliente nel sistema di prenotazione alberghiera.

Gli eventi vengono inviati dal cellulare dei clienti quando vengono rilevati vicino a un beacon. È necessario progettare un app mobile per inviare eventi dal telefono cellulare del cliente al Mobile SDK.

Il campo Membro fedeltà è un campo personalizzato ed è stato aggiunto in XDM per il nostro ID organizzazione specifico.
