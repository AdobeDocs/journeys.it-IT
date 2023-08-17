---
product: adobe campaign
title: Informazioni sulla configurazione delle azioni personalizzata
description: Scopri come configurare un’azione personalizzata
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 7ad2419854b4fcecae7fbb20bdd6a6f2fbc04988
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 12%

---

# Informazioni sulla configurazione delle azioni personalizzata {#concept_sxy_bzs_dgb}

Se utilizzi un sistema di terze parti per l’invio dei messaggi o se desideri [!DNL Journey Orchestration] per inviare chiamate API a un sistema di terze parti, è qui che configuri la relativa connessione a [!DNL Journey Orchestration]. L’azione personalizzata definita dagli utenti tecnici sarà quindi disponibile nella palette a sinistra del percorso, nel **[!UICONTROL Action]** categoria (vedere [questa pagina](../building-journeys/about-action-activities.md). Di seguito sono riportati alcuni esempi di sistemi a cui è possibile connettersi con azioni personalizzate: Epsilon, Facebook, Adobe.io, Firebase, ecc.

Le limitazioni sono elencate in [questa pagina](../about/limitations.md).

Nei parametri delle azioni personalizzati, puoi trasmettere una semplice raccolta e un insieme di oggetti. Per informazioni sulle limitazioni, fare riferimento a [questa pagina](../usecase/collections.md#limitations). Inoltre, i parametri hanno un formato previsto (ad esempio, stringa, decimale e così via). Devi fare attenzione a rispettare questi formati previsti. Fai riferimento a questo [caso d’uso](../usecase/collections.md).

Di seguito sono riportati i passaggi principali necessari per configurare un’azione personalizzata:

1. Dalla sezione **[!UICONTROL Actions]** , fare clic su **[!UICONTROL Add]** per creare una nuova azione. Il riquadro di configurazione delle azioni si apre sul lato destro dello schermo.

   ![](../assets/custom2.png)

1. Immetti un nome per l&#39;azione.

   >[!NOTE]
   >
   >Non utilizzare spazi o caratteri speciali. Non usare più di 30 caratteri.

1. Aggiungi una descrizione all’azione. Questo passaggio è facoltativo.
1. Il numero di percorsi che utilizzano questa azione viene visualizzato nel **[!UICONTROL Used in]** campo. Puoi fare clic su **[!UICONTROL View journeys]** per visualizzare l&#39;elenco dei percorsi che utilizzano questa azione.
1. Definisci i diversi **[!UICONTROL URL Configuration]** parametri. Consulta [questa pagina](../action/url-configuration.md).
1. Configurare **[!UICONTROL Authentication]** sezione. Questa configurazione è la stessa delle origini dati.  Consulta [questa sezione](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definisci il **[!UICONTROL Action parameters]**. Consulta [questa pagina](../action/defining-the-message-parameters.md).
1. Fai clic su **[!UICONTROL Save]**.

   L’azione personalizzata è ora configurata ed è pronta per essere utilizzata nei percorsi. Consulta [questa pagina](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Quando un’azione personalizzata viene utilizzata in un percorso, la maggior parte dei parametri è di sola lettura. È possibile modificare solo **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** campi e **[!UICONTROL Authentication]** sezione.
