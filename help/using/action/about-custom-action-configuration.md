---
title: Informazioni sulla configurazione delle azioni personalizzata
description: Informazioni su come configurare un'azione personalizzata
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 12%

---


# Informazioni sulla configurazione delle azioni personalizzata {#concept_sxy_bzs_dgb}

Se utilizzate un sistema di terze parti per inviare messaggi o se desiderate [!DNL Journey Orchestration] inviare chiamate API a un sistema di terze parti, questo è il punto in cui configurate la connessione a [!DNL Journey Orchestration]. L&#39;azione personalizzata definita dagli utenti tecnici sarà quindi disponibile nella palette a sinistra del percorso, nella **[!UICONTROL Action]** categoria (vedere [](../building-journeys/about-action-activities.md). Di seguito sono riportati alcuni esempi di sistemi a cui è possibile connettersi con azioni personalizzate: Epsilon, Facebook,  Adobe.io, Firebase, ecc.
Le limitazioni sono elencate qui: [](../action/custom-action-limitations.md).

Di seguito sono riportati i passaggi principali necessari per configurare un&#39;azione personalizzata:

1. Dall’ **[!UICONTROL Actions]** elenco, fare clic **[!UICONTROL Add]** per creare una nuova azione. Il riquadro di configurazione delle azioni si apre sul lato destro della schermata.

   ![](../assets/custom2.png)

1. Immettete un nome per l’azione.

   >[!NOTE]
   >
   >Non utilizzare spazi o caratteri speciali. Non usare più di 30 caratteri.

1. Aggiungi una descrizione all&#39;azione. Questo passaggio è facoltativo.
1. The number of journeys that use this action is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. Define the different **[!UICONTROL URL Configuration]** parameters. A questo proposito, consulta la sezione [](../action/url-configuration.md).
1. Configurare la **[!UICONTROL Authentication]** sezione. Questa configurazione è la stessa delle origini dati.  A questo proposito, consulta la sezione [](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definite il **[!UICONTROL Message parameters]**. A questo proposito, consulta la sezione [](../action/defining-the-message-parameters.md).
1. Clic **[!UICONTROL Save]**.

   L&#39;azione personalizzata ora è configurata e pronta per essere utilizzata nei vostri viaggi. A questo proposito, consulta la sezione [](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Quando un&#39;azione personalizzata viene utilizzata in un viaggio, la maggior parte dei parametri sono di sola lettura. È possibile modificare solo i **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** i campi e la **[!UICONTROL Authentication]** sezione.
