---
product: adobe campaign
title: Informazioni sulla configurazione delle azioni personalizzata
description: Scopri come configurare un’azione personalizzata
feature: Percorsi
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 15%

---

# Informazioni sulla configurazione delle azioni personalizzata {#concept_sxy_bzs_dgb}

Se utilizzi un sistema di terze parti per l’invio di messaggi o se desideri che [!DNL Journey Orchestration] invii chiamate API a un sistema di terze parti, puoi configurare la relativa connessione a [!DNL Journey Orchestration]. L’azione personalizzata definita dagli utenti tecnici sarà quindi disponibile nella palette a sinistra del percorso, nella categoria **[!UICONTROL Action]** (consulta [questa pagina](../building-journeys/about-action-activities.md). Di seguito sono riportati alcuni esempi di sistemi a cui è possibile connettersi con azioni personalizzate: Epsilon, Facebook, Adobe.io, Firebase, ecc.
Le limitazioni sono elencate in [questa pagina](../about/limitations.md).

Di seguito sono riportati i passaggi principali necessari per configurare un’azione personalizzata:

1. Dall’elenco **[!UICONTROL Actions]**, fai clic su **[!UICONTROL Add]** per creare una nuova azione. Il riquadro di configurazione delle azioni si apre sul lato destro dello schermo.

   ![](../assets/custom2.png)

1. Immetti un nome per l’azione.

   >[!NOTE]
   >
   >Non utilizzare spazi o caratteri speciali. Non usare più di 30 caratteri.

1. Aggiungi una descrizione all’azione. Questo passaggio è facoltativo.
1. Il numero di percorsi che utilizzano questa azione viene visualizzato nel campo **[!UICONTROL Used in]** . Fai clic sul pulsante **[!UICONTROL View journeys]** per visualizzare l’elenco dei percorsi che utilizzano questa azione.
1. Definisci i diversi parametri **[!UICONTROL URL Configuration]**. Consulta [questa pagina](../action/url-configuration.md).
1. Configura la sezione **[!UICONTROL Authentication]** . Questa configurazione è la stessa delle origini dati.  Vedi [questa sezione](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definisci il **[!UICONTROL Message parameters]**. Consulta [questa pagina](../action/defining-the-message-parameters.md).
1. Fai clic su **[!UICONTROL Save]**.

   L’azione personalizzata è ora configurata ed è pronta per essere utilizzata nei percorsi. Consulta [questa pagina](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Quando un&#39;azione personalizzata viene utilizzata in un percorso, la maggior parte dei parametri è di sola lettura. È possibile modificare solo i campi **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** e la sezione **[!UICONTROL Authentication]**.
