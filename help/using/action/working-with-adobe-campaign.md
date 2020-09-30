---
title: Utilizzo di Adobe Campaign
description: Scopri  azioni Adobe Campaign
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
source-git-commit: 4f7cc4da51a93019b5a296003c51d4bee6724498
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 2%

---


# Utilizzo di Adobe Campaign {#using_adobe_campaign_standard}

Puoi inviare e-mail, notifiche push e SMS utilizzando le  funzionalità di Adobe Campaign Standard Transactional Messaging.

[!DNL Journey Orchestration] viene fornito con un&#39;azione out-of-the-box che consente la connessione a  Adobe Campaign Standard.

Per poter essere utilizzato nel Journey Orchestration, è necessario pubblicare il messaggio di transazione Campaign Standard e il relativo evento associato. Se l&#39;evento è pubblicato ma il messaggio non lo è, non sarà visibile nell&#39;interfaccia dell&#39;Journey Orchestration. Se il messaggio viene pubblicato ma l&#39;evento associato non lo è, sarà visibile nell&#39;interfaccia dell&#39;Journey Orchestration ma non sarà utilizzabile.

>[!NOTE]
>
>Per evitare il sovraccarico  messaggi transazionali Adobe Campaign Standard, si consiglia di impostare una regola **di** capping per l&#39;integrazione dei Campaign Standard.
>
>Per ulteriori informazioni sugli SLA per la messaggistica transazionale, consulta [Descrizione](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)del prodotto Adobe Campaign Standard.

Di seguito sono riportati i passaggi per configurarlo:

1. Dall’ **[!UICONTROL Actions]** elenco, fate clic sull’azione **[!UICONTROL AdobeCampaignStandard]** incorporata. Il riquadro di configurazione delle azioni si apre sul lato destro della schermata.

   ![](../assets/actioncampaign.png)

1. Copiate l’URL dell’istanza  Adobe Campaign Standard e incollatelo nel **[!UICONTROL URL]** campo.

1. Fare clic su per **[!UICONTROL Test the instance URL]** verificare la validità dell&#39;istanza.

   >[!NOTE]
   >
   >Questo test verifica che:
   >
   >L’host è &quot;.campaign.adobe.com&quot; o &quot;.campaign-sandbox.adobe.com&quot;,
   >
   >L&#39;URL inizia con https,
   >
   >L&#39;ORG associato a questa istanza  Adobe Campaign Standard è uguale all&#39;ORG  Journey Orchestration.

Durante la progettazione del percorso, nella **[!UICONTROL Action]** categoria saranno disponibili tre azioni: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (consultate [Utilizzo  azioni](../building-journeys/using-adobe-campaign-actions.md)Adobe Campaign). **L&#39;evento** Reazioni consente inoltre di reagire ai clic dei messaggi, alle aperture e così via. (vedere Eventi [di](../building-journeys/reaction-events.md)reazione).

![](../assets/journey58.png)

Se utilizzi un sistema di terze parti per inviare messaggi, devi aggiungere e configurare un&#39;azione personalizzata. See [About custom action configuration](../action/about-custom-action-configuration.md).
