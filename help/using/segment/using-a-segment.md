---
product: adobe campaign
solution: Journey Orchestration
title: Utilizzo di un segmento
description: Scopri come utilizzare un segmento
feature: Percorsi
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 2%

---


# Utilizzo di segmenti nelle condizioni {#using-a-segment}

Questa sezione spiega come utilizzare un segmento in una condizione di percorso. Per scoprire come utilizzare un evento **[!UICONTROL Segment qualification]** nel percorso, consulta questa [sezione](../building-journeys/segment-qualification-events.md).

Per utilizzare un segmento in una condizione di percorso, effettua le seguenti operazioni:

1. Apri un percorso, rilascia un’attività **[!UICONTROL Condition]** e scegli la **Condizione origine dati**.
   ![](../assets/journey47.png)

1. Fai clic su **[!UICONTROL Add a path]** per ogni percorso aggiuntivo necessario. Per ogni percorso, fai clic sul campo **[!UICONTROL Expression]** .

   ![](../assets/segment3.png)

1. Sul lato sinistro, apri il nodo **[!UICONTROL Segments]** . Trascina e rilascia il segmento da utilizzare per la condizione. Per impostazione predefinita, la condizione sul segmento è vera.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Solo i singoli utenti con gli stati di partecipazione al segmento **Realized** e **Esistenti** saranno considerati membri del segmento. Per ulteriori informazioni su come valutare un segmento, consulta la [documentazione del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Per ulteriori informazioni sulle condizioni di percorso e su come utilizzare l’editor di espressioni semplici, consulta [Attività condizione](../building-journeys/condition-activity.md#about_condition).