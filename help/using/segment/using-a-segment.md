---
product: adobe campaign
title: Utilizzo di un segmento
description: Scopri come utilizzare un segmento
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 2%

---

# Utilizzo di segmenti nelle condizioni {#using-a-segment}

Questa sezione spiega come utilizzare un segmento in una condizione di percorso. Per scoprire come utilizzare un **[!UICONTROL Segment qualification]** nel tuo percorso, fai riferimento a questo [sezione](../building-journeys/segment-qualification-events.md).

Per utilizzare un segmento in una condizione di percorso, effettua le seguenti operazioni:

1. Apri un percorso, rilascia una **[!UICONTROL Condition]** e scegli la **Condizione origine dati**.
   ![](../assets/journey47.png)

1. Fai clic su **[!UICONTROL Add a path]** per ogni percorso aggiuntivo necessario. Per ogni percorso, fai clic sul pulsante **[!UICONTROL Expression]** campo .

   ![](../assets/segment3.png)

1. Sul lato sinistro, svolgersi **[!UICONTROL Segments]** nodo. Trascina e rilascia il segmento da utilizzare per la condizione. Per impostazione predefinita, la condizione sul segmento è vera.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Solo gli individui con il **Realizzato** e **Esistente** gli stati di partecipazione al segmento saranno considerati membri del segmento. Per ulteriori informazioni su come valutare un segmento, consulta [Documentazione del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Per ulteriori informazioni sulle condizioni di percorso e su come utilizzare l’editor di espressioni semplici, consulta [Attività condizione](../building-journeys/condition-activity.md#about_condition).
