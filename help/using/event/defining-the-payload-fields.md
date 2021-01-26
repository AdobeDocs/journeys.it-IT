---
product: adobe campaign
solution: Journey Orchestration
title: Definizione dei campi payload
description: Informazioni su come definire i campi payload
translation-type: tm+mt
source-git-commit: a515e052a5bc1359632a1829df70a206614a5bb2
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 6%

---


# Definizione dei campi payload {#concept_yrw_3qt_52b}

La definizione del payload consente di scegliere le informazioni che il sistema prevede di ricevere dall&#39;evento nel percorso e la chiave per identificare la persona associata all&#39;evento. Il payload si basa sulla definizione del campo XDM del Experience Cloud . Per ulteriori informazioni su XDM, fare riferimento a [questa pagina](https://docs.adobe.com/content/help/it-IT/experience-platform/xdm/home.html).

1. Selezionare uno schema XDM dall&#39;elenco e fare clic sul campo **[!UICONTROL Payload]** o sull&#39;icona **[!UICONTROL Edit]**.

   ![](../assets/journey8.png)

   Vengono visualizzati tutti i campi definiti nello schema. L&#39;elenco dei campi varia da uno schema all&#39;altro. È possibile cercare un campo specifico o utilizzare i filtri per visualizzare tutti i nodi e i campi o solo i campi selezionati. In base alla definizione dello schema, alcuni campi possono essere obbligatori e preselezionati. Non è possibile deselezionarli. Per impostazione predefinita, tutti i campi obbligatori per la ricezione dell’evento da parte del Journey Orchestration sono selezionati.

   >[!NOTE]
   >
   >Accertatevi di aver aggiunto il mixin &quot;orchestrazione&quot; allo schema XDM. In questo modo lo schema contiene tutte le informazioni necessarie per l&#39;utilizzo di [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. Selezionate i campi che prevedete di ricevere dall’evento. Questi sono i campi che l&#39;utente aziendale sfrutterà nel percorso. Devono inoltre includere la chiave che verrà utilizzata per identificare la persona associata all&#39;evento (vedere [questa pagina](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Per gli eventi generati dal sistema, il campo **[!UICONTROL eventID]** viene aggiunto automaticamente nell&#39;elenco dei campi selezionati in modo che [!DNL Journey Orchestration] possa identificare l&#39;evento. Il sistema che preme l&#39;evento non deve generare un ID, ma deve utilizzare quello disponibile nell&#39;anteprima del payload. Consulta [questa pagina](../event/previewing-the-payload.md).

1. Dopo aver selezionato i campi necessari, fare clic su **[!UICONTROL Save]** o premere **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   Il numero di campi selezionati viene visualizzato nel campo **[!UICONTROL Payload]**.

   ![](../assets/journey12.png)
