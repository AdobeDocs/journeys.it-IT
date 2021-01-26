---
product: adobe campaign
solution: Journey Orchestration
title: Utilizzo di Adobe Campaign
description: Scopri  azioni Adobe Campaign
translation-type: tm+mt
source-git-commit: a515e052a5bc1359632a1829df70a206614a5bb2
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 4%

---


# Utilizzo di Adobe Campaign {#using_adobe_campaign_standard}

Puoi inviare e-mail, notifiche push e SMS utilizzando le  funzionalità di Adobe Campaign Standard Transactional Messaging.

[!DNL Journey Orchestration] viene fornito con un&#39;azione out-of-the-box che consente la connessione a  Adobe Campaign Standard.

Per poter essere utilizzato nel Journey Orchestration, è necessario pubblicare il messaggio di transazione Campaign Standard e il relativo evento associato. Se l&#39;evento è pubblicato ma il messaggio non lo è, non sarà visibile nell&#39;interfaccia dell&#39;Journey Orchestration. Se il messaggio viene pubblicato ma l&#39;evento associato non lo è, sarà visibile nell&#39;interfaccia dell&#39;Journey Orchestration ma non sarà utilizzabile.

>[!NOTE]
>
>Una regola di capping di 13 chiamate al secondo viene automaticamente definita per  azioni Adobe Campaign Standard non appena viene impostata &#39;integrazione Adobe Campaign Standard. Questo corrisponde alla scala ufficiale di  Adobe Campaign Standard Transactional Messaging.
>
>Ulteriori informazioni sugli SLA di messaggistica transazionale in [ Descrizione prodotto Adobe Campaign Standard](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html).

Di seguito sono riportati i passaggi per configurarlo:

1. Nell&#39;elenco **[!UICONTROL Actions]**, fare clic sull&#39;azione **[!UICONTROL AdobeCampaignStandard]** incorporata. Il riquadro di configurazione delle azioni si apre sul lato destro della schermata.

   ![](../assets/actioncampaign.png)

1. Copiate l&#39;URL dell&#39;istanza  Adobe Campaign Standard e incollatelo nel campo **[!UICONTROL URL]**.

1. Fare clic su **[!UICONTROL Test the instance URL]** per verificare la validità dell&#39;istanza.

   >[!NOTE]
   >
   >Questo test verifica che:
   >
   >L’host è &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot; o &quot;.campaign-demo.adobe.com&quot;
   >
   >L&#39;URL inizia con https,
   >
   >L&#39;ORG associato a questa istanza  Adobe Campaign Standard è uguale all&#39;ORG  Journey Orchestration.

Durante la progettazione del percorso, nella categoria **[!UICONTROL Action]** saranno disponibili tre azioni: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (vedere [Utilizzo  azioni Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). **Gli** eventi di reazione consentiranno inoltre di reagire ai clic dei messaggi, alle aperture e così via. (vedere [Eventi di reazione](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Se utilizzi un sistema di terze parti per inviare messaggi, devi aggiungere e configurare un&#39;azione personalizzata. Vedere [Informazioni sulla configurazione dell&#39;azione personalizzata](../action/about-custom-action-configuration.md).
