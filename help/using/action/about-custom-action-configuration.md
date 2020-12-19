---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sulla configurazione delle azioni personalizzata
description: Informazioni su come configurare un'azione personalizzata
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 15%

---


# Informazioni sulla configurazione delle azioni personalizzata {#concept_sxy_bzs_dgb}

Se utilizzi un sistema di terze parti per inviare messaggi o se desideri che [!DNL Journey Orchestration] invii chiamate API a un sistema di terze parti, questo è il punto in cui configuri la connessione a [!DNL Journey Orchestration]. L&#39;azione personalizzata definita dagli utenti tecnici sarà quindi disponibile nella palette a sinistra del percorso, nella categoria **[!UICONTROL Action]** (vedere [questa pagina](../building-journeys/about-action-activities.md). Di seguito sono riportati alcuni esempi di sistemi a cui è possibile connettersi con azioni personalizzate: Epsilon, Facebook,  Adobe.io, Firebase, ecc.
Le limitazioni sono elencate in [questa pagina](../about/limitations.md).

Di seguito sono riportati i passaggi principali necessari per configurare un&#39;azione personalizzata:

1. Nell&#39;elenco **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Add]** per creare una nuova azione. Il riquadro di configurazione delle azioni si apre sul lato destro della schermata.

   ![](../assets/custom2.png)

1. Immettete un nome per l’azione.

   >[!NOTE]
   >
   >Non utilizzare spazi o caratteri speciali. Non usare più di 30 caratteri.

1. Aggiungi una descrizione all&#39;azione. Questo passaggio è facoltativo.
1. Il numero di viaggi che utilizzano questa azione viene visualizzato nel campo **[!UICONTROL Used in]**. È possibile fare clic sul pulsante **[!UICONTROL View journeys]** per visualizzare l&#39;elenco dei viaggi che utilizzano questa azione.
1. Definire i diversi parametri **[!UICONTROL URL Configuration]**. Consulta [questa pagina](../action/url-configuration.md).
1. Configurare la sezione **[!UICONTROL Authentication]**. Questa configurazione è la stessa delle origini dati.  Vedi [questa sezione](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definire il **[!UICONTROL Message parameters]**. Consulta [questa pagina](../action/defining-the-message-parameters.md).
1. Fai clic su **[!UICONTROL Save]**.

   L&#39;azione personalizzata ora è configurata e pronta per essere utilizzata nei vostri viaggi. Consulta [questa pagina](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Quando un&#39;azione personalizzata viene utilizzata in un viaggio, la maggior parte dei parametri sono di sola lettura. È possibile modificare solo i campi **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** e la sezione **[!UICONTROL Authentication]**.
