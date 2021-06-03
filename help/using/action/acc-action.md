---
product: adobe campaign
title: Informazioni sull’integrazione di Campaign Classic
description: Scopri l’integrazione con Campaign Classic
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 1712529984af02d0a3f678418db1e819370056d6
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 1%

---

# Utilizzo di Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Questa integrazione ti consente di inviare e-mail, notifiche push e SMS utilizzando le funzionalità di messaggistica transazionale di Adobe Campaign Classic.

La connessione tra le istanze Journey Orchestration e Campaign Classic viene impostata per Adobe al momento del provisioning.

In questa [sezione](../usecase/campaign-classic-use-case.md) viene presentato un caso d’uso end-to-end.

Per ogni azione configurata, nella palette Progettazione percorsi è disponibile un’attività di azione. Fare riferimento a questa sezione [sezione](../building-journeys/using-adobe-campaign-classic.md).

## Note importanti

* I messaggi non sono soggetti a limitazione. Il numero massimo di messaggi che possono essere inviati a 50.000/ora in base al nostro attuale SLA Campaign Classic. Per questo motivo, l’orchestrazione dei Percorsi deve essere utilizzata solo in casi d’uso unitari (eventi individuali, non segmenti).

* È necessario configurare un’azione sull’area di lavoro per modello da utilizzare. Devi configurare un’azione in Journey Orchestration per ogni modello che desideri utilizzare da Adobe Campaign Classic.

* È consigliabile utilizzare un’istanza del Centro messaggi dedicata ospitata per questa integrazione per evitare di influire su altre operazioni di Campaign Classic in corso. Il server di marketing può essere ospitato o on-premise. La build richiesta è 21.1 Release Candidate o successiva.

* Non esiste una convalida che attesti che il payload o il messaggio Campaign Classic è corretto.

* Non è possibile utilizzare un’azione Campaign Classic con un evento di qualificazione dei segmenti.

## Prerequisiti

In Campaign Classic, devi creare e pubblicare un messaggio transazionale e il relativo evento associato. Consulta la [documentazione Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Puoi creare il payload JSON corrispondente a ciascun messaggio seguendo il pattern seguente. Quindi incolla questo payload durante la configurazione dell’azione in Journey Orchestration (vedi sotto)

Ecco un esempio:

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

* **canale**: il canale definito per il modello transazionale di Campaign Classic
* **eventType**: il nome interno dell’evento Campaign Classic
* **ctx**: in base alla personalizzazione contenuta nel messaggio.

## Configurazione dell’azione

Al Journey Orchestration, devi configurare un’azione per messaggio transazionale. Segui questi passaggi:

1. Crea una nuova azione. Fare riferimento a questa sezione [sezione](../action/action.md).
1. Immetti un nome e una descrizione.
1. Nel campo **Tipo azione**, seleziona **Adobe Campaign Classic**.
1. Fai clic sul campo **Payload** e incolla un esempio del payload JSON corrispondente al messaggio Campaign Classic. Per ottenere questo payload, contatta l’Adobe .
1. Regola i diversi campi in modo che siano statici o variabili a seconda di se desideri mapparli sull’area di lavoro del Percorso. Alcuni campi, come i parametri del canale per l’indirizzo e-mail e i campi di personalizzazione (ctx), probabilmente dovranno essere definiti come variabili da mappare nel contesto del percorso.
1. Fai clic su **Salva**.

![](../assets/accintegration1.png)


