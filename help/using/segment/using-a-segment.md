---
product: adobe campaign
title: Utilizzo di segmenti nelle condizioni
description: Scopri come utilizzare un segmento
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---

# Utilizzo di segmenti nelle condizioni {#using-a-segment}

Questa sezione spiega come utilizzare un segmento in una condizione di percorso. Per scoprire come utilizzare un **[!UICONTROL Segment qualification]** nel tuo percorso, fai riferimento a questo [sezione](../building-journeys/segment-qualification-events.md).

Per utilizzare un segmento in una condizione di percorso, effettua le seguenti operazioni:

1. Apri un percorso, rilascia una **[!UICONTROL Condition]** e scegli la **Condizione origine dati**.
   ![](../assets/journey47.png)

1. Clic **[!UICONTROL Add a path]** per ogni percorso aggiuntivo necessario. Per ogni percorso, fai clic su **[!UICONTROL Expression]** campo.

   ![](../assets/segment3.png)

1. Sul lato sinistro, apri **[!UICONTROL Segments]** nodo. Trascina e rilascia il segmento da utilizzare per la condizione. Per impostazione predefinita, la condizione sul segmento è true.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Solo i singoli utenti con **Realizzato** e **Esistente** gli stati di partecipazione al segmento verranno considerati come membri del segmento. Per ulteriori informazioni su come valutare un segmento, consulta [Documentazione del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Per ulteriori informazioni sulle condizioni del percorso e su come utilizzare l’editor di espressioni semplici, consulta [Attività condizione](../building-journeys/condition-activity.md#about_condition).
