---
product: adobe campaign
title: Utilizzo di Adobe Campaign
description: Informazioni sulle azioni di Adobe Campaign
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: c49908d36ecbc68ae11b5621305f39dd59c67871
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 2%

---

# Utilizzo di Adobe Campaign {#using_adobe_campaign}

## Utilizzo di Adobe Campaign Standard {#using_adobe_campaign_standard}

Puoi inviare e-mail, notifiche push e SMS utilizzando le funzionalità di messaggistica transazionale di Adobe Campaign Standard.

[!DNL Journey Orchestration] viene fornito con un’azione standard che consente la connessione ad Adobe Campaign Standard.

Per poter essere utilizzato nel Journey Orchestration, il messaggio transazionale di Campaign Standard e il relativo evento associato devono essere pubblicati. Se l’evento è pubblicato ma il messaggio non lo è, non sarà visibile nell’interfaccia di Journey Orchestration. Se il messaggio viene pubblicato ma l’evento associato non lo è, sarà visibile nell’interfaccia di Journey Orchestration ma non sarà utilizzabile.

>[!NOTE]
>
>Una regola di limitazione di 13 chiamate al secondo viene definita automaticamente per le azioni di Adobe Campaign Standard non appena viene impostata l’integrazione di Adobe Campaign Standard. Questo corrisponde alla scala ufficiale dei messaggi transazionali Adobe Campaign Standard.
>
>Ulteriori informazioni sugli SLA di messaggistica transazionale in [Descrizione del prodotto Adobe Campaign Standard](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html).

Di seguito sono riportati i passaggi per configurarlo:

1. Dall’elenco **[!UICONTROL Actions]**, fai clic sull’azione incorporata **[!UICONTROL AdobeCampaignStandard]**. Il riquadro di configurazione delle azioni si apre sul lato destro dello schermo.

   ![](../assets/actioncampaign.png)

1. Copia l’URL dell’istanza Adobe Campaign Standard e incollalo nel campo **[!UICONTROL URL]** .

1. Fai clic su **[!UICONTROL Test the instance URL]** per verificare la validità dell’istanza.

   >[!NOTE]
   >
   >Questo test verifica che:
   >
   >L’host è &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot;&quot; o &quot;.adls.adobe.com&quot;.
   >
   >L’URL inizia con https,
   >
   >L&#39;ORG associato a questa istanza Adobe Campaign Standard è lo stesso dell&#39;ORG del Journey Orchestration.

Durante la progettazione del percorso, nella categoria **[!UICONTROL Action]** saranno disponibili tre azioni: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (consulta [Utilizzo di azioni Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). **Gli** eventi Reactions ti consentono inoltre di reagire ai clic dei messaggi, agli aperture e così via. (consulta [Eventi di reazione](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Se utilizzi un sistema di terze parti per l’invio dei messaggi, devi aggiungere e configurare un’azione personalizzata. Consulta [Informazioni sulla configurazione delle azioni personalizzate](../action/about-custom-action-configuration.md).

## Utilizzo di Adobe Campaign v7/v8 {#using_adobe_campaign_v7_v8}

Questa integrazione è disponibile per Adobe Campaign Classic v7 a partire dalla versione 21.1 e Adobe Campaign v8. Ti consente di inviare e-mail, notifiche push e SMS utilizzando le funzionalità di messaggistica transazionale di Adobe Campaign.

La connessione tra le istanze del Journey Orchestration e di Campaign viene impostata per Adobe al momento del provisioning.

In questa [sezione](../usecase/campaign-v7-v8-use-case.md) viene presentato un caso d’uso end-to-end.

Per ogni azione configurata, nella palette Progettazione percorsi è disponibile un’attività di azione. Fare riferimento a questa sezione [sezione](../building-journeys/using-adobe-campaign-actions.md).

### Note importanti

* I messaggi non sono soggetti a limitazione. Il numero massimo di messaggi che possono essere inviati oltre 50.000/ora in base al nostro attuale SLA Campaign. Per questo motivo, l’orchestrazione dei Percorsi deve essere utilizzata solo in casi d’uso unitari (eventi individuali, non segmenti).

* È necessario configurare un’azione sull’area di lavoro per modello da utilizzare. Devi configurare un’azione in Journey Orchestration per ogni modello che desideri utilizzare da Adobe Campaign.

* È consigliabile utilizzare un’istanza del Centro messaggi dedicata ospitata per questa integrazione per evitare di influenzare altre operazioni di Campaign che potrebbero essere in corso. Il server di marketing può essere ospitato o on-premise. La build richiesta è 21.1 Release Candidate o successiva.

* Non esiste una convalida relativa alla correttezza del payload o del messaggio Campaign.

* Non puoi utilizzare un’azione Campaign con un evento di qualificazione dei segmenti.

### Prerequisiti

In Campaign, devi creare e pubblicare un messaggio transazionale e il relativo evento associato. Consulta la [documentazione Adobe Campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

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

* **canale**: il canale definito per il modello transazionale di Campaign
* **eventType**: il nome interno dell’evento Campaign
* **ctx**: in base alla personalizzazione contenuta nel messaggio.

### Configurazione dell’azione

Al Journey Orchestration, devi configurare un’azione per messaggio transazionale. Segui questi passaggi:

1. Crea una nuova azione. Fare riferimento a questa sezione [sezione](../action/action.md).
1. Immetti un nome e una descrizione.
1. Nel campo **Tipo azione**, seleziona **Adobe Campaign Classic**.
1. Fai clic nel campo **Payload** e incolla un esempio del payload JSON corrispondente al messaggio Campaign. Per ottenere questo payload, contatta l’Adobe .
1. Regola i diversi campi in modo che siano statici o variabili a seconda di se desideri mapparli sull’area di lavoro del Percorso. Alcuni campi, come i parametri del canale per l’indirizzo e-mail e i campi di personalizzazione (ctx), probabilmente dovranno essere definiti come variabili da mappare nel contesto del percorso.
1. Fai clic su **Salva**.

![](../assets/accintegration1.png)


