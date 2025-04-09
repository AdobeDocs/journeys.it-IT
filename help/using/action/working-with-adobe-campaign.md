---
product: adobe campaign
title: Utilizzo di Adobe Campaign
description: Scopri le azioni di Adobe Campaign
feature: Journeys
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 2%

---

# Utilizzo di Adobe Campaign Standard {#using_adobe_campaign_standard}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


Puoi inviare e-mail, notifiche push e SMS utilizzando le funzionalità di messaggistica transazionale di Adobe Campaign Standard.

[!DNL Journey Orchestration] viene fornito con un&#39;azione preconfigurata che consente la connessione ad Adobe Campaign Standard.

Per poter essere utilizzato in Journey Orchestration, il messaggio transazionale di Campaign Standard e il relativo evento associato devono essere pubblicati. Se l’evento viene pubblicato ma il messaggio non lo è, non sarà visibile nell’interfaccia di Journey Orchestration. Se il messaggio viene pubblicato ma il relativo evento associato non lo è, sarà visibile nell’interfaccia di Journey Orchestration ma non sarà utilizzabile.

>[!NOTE]
>
>Una regola di limite di 4000 chiamate al minuto 5 viene definita automaticamente per le azioni Adobe Campaign Standard non appena viene impostata l’integrazione con Adobe Campaign Standard. Ciò corrisponde alla scala ufficiale di Adobe Campaign Standard Transactional Messaging.
>
>Ulteriori informazioni sugli SLA per la messaggistica transazionale in [Descrizione del prodotto Adobe Campaign Standard](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html).

Di seguito sono riportati i passaggi per configurarlo:

1. Nell&#39;elenco **[!UICONTROL Actions]** fare clic sull&#39;azione predefinita **[!UICONTROL AdobeCampaignStandard]**. Il riquadro di configurazione delle azioni si apre sul lato destro dello schermo.

   ![](../assets/actioncampaign.png)

1. Copia l&#39;URL dell&#39;istanza di Adobe Campaign Standard e incollalo nel campo **[!UICONTROL URL]**.

1. Fare clic su **[!UICONTROL Test the instance URL]** per verificare la validità dell&#39;istanza.

   >[!NOTE]
   >
   >Questo test verifica che:
   >
   >L’host è &quot;.campaign.adobe.com&quot;, &quot;.campaign-sandbox.adobe.com&quot;, &quot;.campaign-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; o &quot;.adls.adobe.com&quot;.
   >
   >L’URL inizia con https,
   >
   >L’ORGANIZZAZIONE associata a questa istanza di Adobe Campaign Standard è la stessa dell’ORGANIZZAZIONE di Journey Orchestration.

Durante la progettazione del percorso, sono disponibili tre azioni nella categoria **[!UICONTROL Action]**: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (vedere [Utilizzo delle azioni di Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md)). **Evento reazioni** ti consentirà inoltre di reagire ai clic sui messaggi, alle aperture e così via. (vedi [Eventi di reazione](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Se utilizzi un sistema di terze parti per l’invio dei messaggi, devi aggiungere e configurare un’azione personalizzata. Consulta [Informazioni sulla configurazione delle azioni personalizzata](../action/about-custom-action-configuration.md).
