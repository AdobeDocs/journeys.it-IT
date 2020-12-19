---
product: adobe campaign
solution: Journey Orchestration
title: Utilizzo di Adobe Campaign
description: Scopri  azioni Adobe Campaign
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Utilizzo di Adobe Campaign {#using_adobe_campaign_standard}

Puoi inviare e-mail, notifiche push e SMS utilizzando le  funzionalità di Adobe Campaign Standard Transactional Messaging.

[!DNL Journey Orchestration] viene fornito con un&#39;azione out-of-the-box che consente la connessione a  Adobe Campaign Standard.

Per poter essere utilizzato nel Journey Orchestration, è necessario pubblicare il messaggio di transazione Campaign Standard e il relativo evento associato. Se l&#39;evento è pubblicato ma il messaggio non lo è, non sarà visibile nell&#39;interfaccia dell&#39;Journey Orchestration. Se il messaggio viene pubblicato ma l&#39;evento associato non lo è, sarà visibile nell&#39;interfaccia dell&#39;Journey Orchestration ma non sarà utilizzabile.

>[!NOTE]
>
> messaggi transazionali Adobe Campaign Standard ha una scala di 50 000 messaggi all&#39;ora al massimo tra i canali per una determinata istanza. Per ridurre il rischio di sovraccarico, si consiglia di impostare una **regola di capping** per l&#39;integrazione dei Campaign Standard.
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
   >L’host è &quot;.campaign.adobe.com&quot; o &quot;.campaign-sandbox.adobe.com&quot;,
   >
   >L&#39;URL inizia con https,
   >
   >L&#39;ORG associato a questa istanza  Adobe Campaign Standard è uguale all&#39;ORG  Journey Orchestration.

Durante la progettazione del percorso, nella categoria **[!UICONTROL Action]** saranno disponibili tre azioni: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (vedere [Utilizzo  azioni Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). **Gli** eventi di reazione consentiranno inoltre di reagire ai clic dei messaggi, alle aperture e così via. (vedere [Eventi di reazione](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Se utilizzi un sistema di terze parti per inviare messaggi, devi aggiungere e configurare un&#39;azione personalizzata. Vedere [Informazioni sulla configurazione dell&#39;azione personalizzata](../action/about-custom-action-configuration.md).
