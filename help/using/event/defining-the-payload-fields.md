---
title: Definizione dei campi payload
description: Informazioni su come definire i campi payload
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Definizione dei campi payload {#concept_yrw_3qt_52b}

La definizione del payload consente di scegliere le informazioni che il sistema prevede di ricevere dall’evento nel percorso e la chiave per identificare quale persona è associata all’evento. Il payload si basa sulla definizione del campo Experience Cloud XDM. Per ulteriori informazioni su XDM, fare riferimento a questa [pagina](https://www.adobe.io/apis/cloudplatform/dataservices/xdm.html).

1. Selezionare uno schema XDM dall&#39;elenco e fare clic sul **[!UICONTROL Payload]**campo o sull&#39;**[!UICONTROL Edit]** icona.

   ![](../assets/journey8.png)

   Vengono visualizzati tutti i campi definiti nello schema. L&#39;elenco dei campi varia da uno schema all&#39;altro. È possibile cercare un campo specifico o utilizzare i filtri per visualizzare tutti i nodi e i campi o solo i campi selezionati. In base alla definizione dello schema, alcuni campi possono essere obbligatori e preselezionati. Non è possibile deselezionarli.

   >[!NOTE]
   >
   >Accertatevi di aver aggiunto il mixin &quot;orchestrazione&quot; allo schema XDM. In questo modo lo schema contiene tutte le informazioni necessarie per l&#39;utilizzo dell&#39;orchestrazione del percorso.

   ![](../assets/journey9.png)

1. Selezionate i campi che prevedete di ricevere dall’evento. Questi sono i campi che l&#39;utente aziendale sfrutterà nel viaggio. Devono inoltre includere la chiave che verrà utilizzata per identificare la persona associata all&#39;evento (vedere [](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Il **[!UICONTROL eventID]**campo viene aggiunto automaticamente nell&#39;elenco dei campi selezionati in modo che l&#39;orchestrazione del viaggio possa identificare l&#39;evento. Il sistema che preme l&#39;evento non deve generare un ID, ma deve utilizzare quello disponibile nell&#39;anteprima del payload. Vedere[](../event/previewing-the-payload.md).

1. Dopo aver selezionato i campi necessari, fate clic **[!UICONTROL Save]**o premete**[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   Nel **[!UICONTROL Payload]**campo viene visualizzato il numero di campi selezionati.

   ![](../assets/journey12.png)
