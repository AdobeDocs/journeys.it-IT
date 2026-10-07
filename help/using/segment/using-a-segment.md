---
product: adobe campaign
title: Utilizzo di segmenti nelle condizioni
description: Scopri come utilizzare un segmento
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 27%
---
# Utilizzo di segmenti nelle condizioni {#using-a-segment}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._


Questa sezione spiega come utilizzare un segmento in una condizione di percorso. Per informazioni su come utilizzare un evento **[!UICONTROL Segment qualification]** nel percorso, fare riferimento a questa [sezione](../building-journeys/segment-qualification-events.md).

Per utilizzare un segmento in una condizione di percorso, effettua le seguenti operazioni:

1. Apri un percorso, rilascia un&#39;attività **[!UICONTROL Condition]** e scegli la **Condizione Source dati**.
   ![](../assets/journey47.png)

1. Fare clic su **[!UICONTROL Add a path]** per ogni percorso aggiuntivo necessario. Per ogni percorso, fare clic sul campo **[!UICONTROL Expression]**.

   ![](../assets/segment3.png)

1. Sul lato sinistro, apri **[!UICONTROL Segments]** nodo. Trascina e rilascia il segmento da utilizzare per la condizione. Per impostazione predefinita, la condizione sul segmento è true.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Solo i singoli utenti con gli stati di partecipazione al segmento **Realizzato** e **Esistente** verranno considerati membri del segmento. Per ulteriori informazioni su come valutare un segmento, consulta la [documentazione del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=it#interpret-segment-results).

Per ulteriori informazioni sulle condizioni del percorso e su come utilizzare l&#39;editor di espressioni semplici, vedere [Attività condizione](../building-journeys/condition-activity.md#about_condition).
