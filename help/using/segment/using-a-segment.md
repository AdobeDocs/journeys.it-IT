---
product: adobe campaign
title: Utilizzo di segmenti nelle condizioni
description: Scopri come utilizzare un segmento
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 4%

---

# Utilizzo di segmenti nelle condizioni {#using-a-segment}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


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
   >Solo i singoli utenti con gli stati di partecipazione al segmento **Realizzato** e **Esistente** verranno considerati membri del segmento. Per ulteriori informazioni su come valutare un segmento, consulta la [documentazione del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Per ulteriori informazioni sulle condizioni del percorso e su come utilizzare l&#39;editor di espressioni semplici, vedere [Attività condizione](../building-journeys/condition-activity.md#about_condition).
