---
product: adobe campaign
title: Informazioni sul caso d’uso avanzato
description: Scopri di più sul caso d’uso avanzato del percorso
feature: Journeys
role: User
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 17%
---
# Informazioni sul caso d’uso avanzato{#concept_vzy_ncy_w2b}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._


## Scopo {#purpose}

Prendiamo l&#39;esempio di un marchio di hotel chiamato Marlton. Nei loro hotel, hanno posizionato dispositivi beacon vicino a tutte le aree strategiche: hall, piani, ristorante, palestra, piscina, ecc.

>[!NOTE]
>
>In questo caso d’uso, usiamo Adobe Campaign Standard per inviare messaggi.

In questo caso d’uso, vedremo come inviare messaggi personalizzati in tempo reale ai clienti quando si trovano vicino a un beacon specifico.

Prima di tutto, vogliamo inviare un messaggio non appena una persona entra in un hotel di Marlton. Vogliamo inviare un messaggio solo se la persona non ha ricevuto alcuna comunicazione da noi nelle ultime 24 ore.

Verifichiamo quindi due condizioni:

* Se questa persona non è un membro fedeltà, gli inviamo un’e-mail per partecipare all’offerta di iscrizione fedeltà.
* Se questa persona è già un membro fedeltà, verifichiamo se ha una prenotazione di camera:
  * In caso contrario, gli invieremo una notifica push con le tariffe delle camere.
  * Se lo fa, gli inviamo una notifica push di benvenuto. E se entra nel ristorante entro le 6 ore successive, gli inviamo una notifica push con uno sconto su un pasto.

![](../assets/journeyuc2_29.png)

Per questo caso d&#39;uso, dovremo creare due eventi (vedi [questa pagina](../usecase/configuring-the-events.md)):

* L&#39;evento beacon della hall che verrà inviato al sistema quando un cliente entra nell&#39;hotel.
* L’evento beacon del ristorante che verrà inviato quando un cliente entra nel ristorante.

Sarà necessario configurare una connessione a due origini dati (vedere [questa pagina](../usecase/configuring-the-data-sources.md)):

* L’origine dati integrata di Adobe Experience Platform, per recuperare le informazioni relative alle due condizioni (iscrizione fedeltà e data dell’ultimo contatto) e le informazioni sulla personalizzazione del messaggio.
* Il sistema di prenotazione dell’hotel, per recuperare le informazioni sullo stato della prenotazione.

## Prerequisiti {#prerequisites}

Per il nostro caso d’uso, abbiamo progettato tre modelli di messaggistica transazionale di Adobe Campaign Standard. Stiamo utilizzando modelli di messaggistica transazionale di eventi. Consulta [questa pagina](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=it).

Adobe Campaign Standard è configurato per l’invio di e-mail e notifiche push.

L’Experience Cloud ID viene utilizzato come chiave per identificare il cliente nel sistema di prenotazione dell’hotel.

Gli eventi vengono inviati dal telefono cellulare dei clienti quando vengono rilevati vicino a un beacon. È necessario progettare un’app mobile per inviare eventi dal telefono cellulare del cliente al SDK mobile.

Il campo del membro Fedeltà è un campo personalizzato ed è stato aggiunto in XDM per l’ID organizzazione specifico.
