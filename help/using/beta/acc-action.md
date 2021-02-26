---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sull'integrazione Campaign Classic
description: Informazioni sull'integrazione Campaign Classic
hide: true
hidefromtoc: true
translation-type: tm+mt
source-git-commit: 937b7235d41fe7f0395e303736974e32eea8558f
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 1%

---


# Integrazione con Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Questa integrazione consente di inviare e-mail, notifiche push e SMS utilizzando le funzionalità di Adobe Campaign Classic Transactional Messaging.

La connessione tra le istanze del Journey Orchestration e del Campaign Classic viene impostata da  Adobe al momento del provisioning.

>[!CAUTION]
>
> Questa integrazione viene rilasciata come versione beta privata. Non è disponibile per tutti i clienti del Journey Orchestration.

## Note importanti

* Non c&#39;è limitazione dei messaggi. Il numero massimo di messaggi che possono essere inviati a 50.000/ora in base al nostro attuale SLA Campaign Classic. Per questo motivo, l&#39;orchestrazione Percorso dovrebbe essere utilizzata solo in casi di utilizzo unitario (eventi individuali, non segmenti).

* È necessario configurare un’azione sul quadro per modello da utilizzare.

* È consigliabile utilizzare un&#39;istanza del Centro messaggi dedicata ospitata per questa integrazione per evitare di influenzare altre operazioni Campaign Classic che potrebbero essere in corso. Il server di marketing può essere ospitato o locale. La build richiesta è 21.1 Release Candidate.

* Non è disponibile alcuna convalida per verificare che il payload o il messaggio Campaign Classic sia corretto.

* Non è possibile utilizzare un&#39;azione Campaign Classic con una qualifica di segmento.

## Prerequisiti

In Campaign Classic , è necessario creare e pubblicare un messaggio transazionale e il relativo evento associato. Fare riferimento alla [documentazione Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Contatta  Adobe per ottenere il payload JSON corrispondente a ciascun messaggio. Quindi, incollerete questo payload durante la configurazione dell&#39;azione nell&#39;Journey Orchestration (vedere di seguito).

Esempio:

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

## Configurazione dell’azione

Ad Journey Orchestration, devi configurare un’azione per messaggio transazionale. Effettuate le seguenti operazioni:

1. Crea una nuova azione. Fare riferimento a questa sezione [](../action/action.md).
1. Immettete un nome e una descrizione.
1. Nel campo **Tipo azione**, selezionare **Adobe Campaign Classic**.
1. Fare clic nel campo **Payload** e incollare un esempio del payload JSON corrispondente al messaggio Campaign Classic. Contatta  Adobe per ottenere questo payload.
1. Regola i diversi campi. Alcuni campi, come i parametri dei canali e i campi di personalizzazione (ctx), devono essere definiti come variabili.
1. Fai clic su **Salva**.

![](../assets/accintegration1.png)

Per ogni azione configurata, nella palette Progettazione percorsi è disponibile un&#39;attività di azione.

## Aggiunta di un messaggio in un percorso

1. Progettare il percorso, a partire da un evento. Vedere la sezione [](../building-journeys/journey.md).
1. Nella sezione **Azione** della palette, selezionare un&#39;azione Campaign Classic e aggiungerla al percorso.
1. Nei **parametri dell&#39;azione** vengono visualizzati tutti i campi previsti nel payload del messaggio. È necessario mappare ciascuno di questi campi con il campo che si desidera utilizzare, sia dall&#39;evento che dall&#39;origine dati. È simile alle azioni personalizzate. Fare riferimento a questa sezione [](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)

