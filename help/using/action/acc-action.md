---
product: adobe campaign
title: Informazioni sull’integrazione di Campaign v7/v8
description: Scopri l’integrazione con Campaign v7/v8
feature: Journeys
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 13%

---

# Utilizzo di Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}

Questa integrazione è disponibile per Adobe Campaign Classic v7 a partire dalla versione 21.1 e per Adobe Campaign v8. Consente di inviare e-mail, notifiche push e SMS utilizzando le funzionalità di messaggistica transazionale di Adobe Campaign.

La connessione tra le istanze Journey Orchestration e Campaign viene impostata da Adobe al momento del provisioning.

Un caso d’uso end-to-end è presentato in questo [sezione](../usecase/campaign-classic-use-case.md).

Per ogni azione configurata, nella palette di Progettazione percorsi è disponibile un’attività di azione. Fai riferimento a questa [sezione](../building-journeys/using-adobe-campaign-classic.md).

## Note importanti

* Non esiste alcuna limitazione dei messaggi. In base al contratto di servizio per le campagne corrente, il numero di messaggi che possono essere inviati è limitato a 50.000/ora. Per questo motivo, l’orchestrazione del Percorso deve essere utilizzata solo in casi d’uso unitari (singoli eventi, non segmenti).

* Devi configurare un’azione nell’area di lavoro per modello da utilizzare. Devi configurare un’azione in Journey Orchestration per ogni modello da utilizzare da Adobe Campaign.

* È consigliabile utilizzare un’istanza dedicata del Centro messaggi ospitata per questa integrazione per evitare di influenzare eventuali altre operazioni di Campaign in corso. Il server di marketing può essere in hosting o on-premise. La build richiesta è 21.1 Release Candidate o successiva.

* Non esiste alcuna convalida che dimostri che il payload o il messaggio di Campaign sono corretti.

* Non è possibile utilizzare un’azione Campaign con un evento di qualificazione dei segmenti.

## Prerequisiti

In Campaign, devi creare e pubblicare un messaggio transazionale e il relativo evento associato. Consulta la sezione [Documentazione di Adobe Campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Puoi creare il payload JSON corrispondente a ciascun messaggio seguendo il pattern indicato di seguito. Incolla quindi questo payload durante la configurazione dell’azione in Journey Orchestration (vedi sotto)

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

* **channel**: il canale definito per il modello transazionale di Campaign
* **eventType**: il nome interno dell’evento Campaign
* **ctx**: variabile basata sulla personalizzazione disponibile nel messaggio.

## Configurazione dell’azione

In Journey Orchestration, devi configurare un’azione per ogni messaggio transazionale. Segui questi passaggi:

1. Crea una nuova azione. Fai riferimento a questa [sezione](../action/action.md).
1. Immettere un nome e una descrizione.
1. In **Tipo di azione** campo, seleziona **Adobe Campaign Classic**.
1. Fai clic su nella **Payload** e incolla un esempio del payload JSON corrispondente al messaggio Campaign. Contatta l’Adobe per ottenere questo payload.
1. Imposta i diversi campi in modo che siano statici o variabili a seconda che desideri mapparli sull’area di lavoro del Percorso. Alcuni campi, come i parametri del canale per l’indirizzo e-mail e i campi di personalizzazione (ctx), probabilmente dovranno essere definiti come variabili da mappare nel contesto del percorso.
1. Fai clic su **Salva**.

![](../assets/accintegration1.png)


