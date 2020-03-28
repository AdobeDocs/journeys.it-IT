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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0c34ce9723168db3a35e3c5de122eae3462b83c0

---


# Informazioni sulla configurazione delle azioni personalizzata {#concept_sxy_bzs_dgb}

Se si utilizza un sistema di terze parti per inviare messaggi o se si desidera che l&#39;orchestrazione del percorso invii chiamate API a un sistema di terze parti, è in questo punto che si configura la relativa connessione all&#39;orchestrazione del percorso. L&#39;azione personalizzata definita dagli utenti tecnici sarà quindi disponibile nella palette a sinistra del percorso, nella **[!UICONTROL Action]** categoria (vedere [](../building-journeys/about-action-activities.md). Di seguito sono riportati alcuni esempi di sistemi a cui è possibile connettersi con azioni personalizzate: Epsilon, Facebook, Adobe.io, Firebase, ecc.
Le limitazioni sono elencate qui: [](../action/custom-action-limitations.md).

Di seguito sono riportati i passaggi principali necessari per configurare un&#39;azione personalizzata:

1. Dall’ **[!UICONTROL Actions]** elenco, fare clic **[!UICONTROL Add]** per creare una nuova azione. Il riquadro di configurazione delle azioni si apre sul lato destro della schermata.

   ![](../assets/custom2.png)

1. Immettete un nome per l’azione.

   >[!NOTE]
   >
   >Non utilizzate spazi o caratteri speciali. Non utilizzare più di 30 caratteri.

1. Aggiungi una descrizione all&#39;azione. Questo passaggio è facoltativo.
1. Il numero di viaggi che utilizzano questa azione viene visualizzato nel **[!UICONTROL Used in]** campo. Puoi fare clic sul **[!UICONTROL View journeys]** pulsante per visualizzare l’elenco dei viaggi che utilizzano questa azione.
1. Definire i diversi **[!UICONTROL URL Configuration]** parametri. Vedere [](../action/url-configuration.md).
1. Configurare la **[!UICONTROL Authentication]** sezione. Questa configurazione è la stessa delle origini dati.  Vedere [](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definite il **[!UICONTROL Message parameters]**. Vedere [](../action/defining-the-message-parameters.md).
1. Clic **[!UICONTROL Save]**.

   L&#39;azione personalizzata ora è configurata e pronta per essere utilizzata nei vostri viaggi. Vedere [](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Quando un&#39;azione personalizzata viene utilizzata in una versione di viaggio, la maggior parte dei parametri sono di sola lettura. È possibile modificare solo i **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** i campi e la **[!UICONTROL Authentication]** sezione.
