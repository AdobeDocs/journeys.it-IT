---
product: adobe campaign
title: Utilizzo di Adobe Campaign
description: Informazioni sulle azioni di Adobe Campaign
feature: Journeys
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# Utilizzo di Adobe Campaign Standard {#using_adobe_campaign_standard}

Puoi inviare e-mail, notifiche push e SMS utilizzando le funzionalità di messaggistica transazionale di Adobe Campaign Standard.

[!DNL Journey Orchestration] viene fornito con un’azione standard che consente la connessione ad Adobe Campaign Standard.

Per poter essere utilizzato nel Journey Orchestration, il messaggio transazionale di Campaign Standard e il relativo evento associato devono essere pubblicati. Se l’evento è pubblicato ma il messaggio non lo è, non sarà visibile nell’interfaccia di Journey Orchestration. Se il messaggio viene pubblicato ma l’evento associato non lo è, sarà visibile nell’interfaccia di Journey Orchestration ma non sarà utilizzabile.

>[!NOTE]
>
>Una regola di limitazione di 13 chiamate al secondo viene definita automaticamente per le azioni di Adobe Campaign Standard non appena viene impostata l’integrazione di Adobe Campaign Standard. Questo corrisponde alla scala ufficiale dei messaggi transazionali Adobe Campaign Standard.
>
>Ulteriori informazioni sugli SLA di messaggistica transazionale in [Descrizione del prodotto Adobe Campaign Standard](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html).

Di seguito sono riportati i passaggi per configurarlo:

1. Da **[!UICONTROL Actions]** fare clic sull&#39;elenco incorporato **[!UICONTROL AdobeCampaignStandard]** azione. Il riquadro di configurazione delle azioni si apre sul lato destro dello schermo.

   ![](../assets/actioncampaign.png)

1. Copia l’URL dell’istanza di Adobe Campaign Standard e incollalo nel **[!UICONTROL URL]** campo .

1. Fai clic sul pulsante **[!UICONTROL Test the instance URL]** per verificare la validità dell’istanza.

   >[!NOTE]
   >
   >Questo test verifica che:
   >
   >L’host è &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot;&quot; o &quot;.adls.adobe.com&quot;.
   >
   >L’URL inizia con https,
   >
   >L&#39;ORG associato a questa istanza Adobe Campaign Standard è lo stesso dell&#39;ORG del Journey Orchestration.

Durante la progettazione del percorso, saranno disponibili tre azioni nella sezione **[!UICONTROL Action]** categoria: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (vedi [Utilizzo delle azioni di Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). **Evento Reazioni** ti consentirà inoltre di reagire ai clic, alle aperture e così via dei messaggi. (vedi [Eventi di reazione](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Se utilizzi un sistema di terze parti per l’invio dei messaggi, devi aggiungere e configurare un’azione personalizzata. Vedi [Informazioni sulla configurazione delle azioni personalizzata](../action/about-custom-action-configuration.md).
