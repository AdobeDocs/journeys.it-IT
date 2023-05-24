---
product: adobe campaign
title: Definizione dei campi payload
description: Scopri come definire i campi payload
feature: Journeys
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 5%

---

# Definizione dei campi payload {#concept_yrw_3qt_52b}

La definizione del payload consente di scegliere le informazioni che il sistema si aspetta di ricevere dall’evento nel percorso e la chiave per identificare quale persona è associata all’evento. Il payload si basa sulla definizione del campo XDM di Experience Cloud. Per ulteriori informazioni su XDM, consulta [questa pagina](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it).

1. Seleziona uno schema XDM dall’elenco e fai clic sul pulsante **[!UICONTROL Payload]** campo o sul **[!UICONTROL Edit]** icona.

   ![](../assets/journey8.png)

   Vengono visualizzati tutti i campi definiti nello schema. L’elenco dei campi varia da uno schema all’altro. Puoi cercare un campo specifico o utilizzare i filtri per visualizzare tutti i nodi e i campi o solo i campi selezionati. In base alla definizione dello schema, alcuni campi possono essere obbligatori e preselezionati. Non è possibile deselezionarli. Per impostazione predefinita, vengono selezionati tutti i campi obbligatori per la corretta ricezione dell’evento per Journey Orchestration.

   >[!NOTE]
   >
   >Assicurati di aver aggiunto il mixin &quot;orchestrazione&quot; allo schema XDM. In questo modo lo schema conterrà tutte le informazioni necessarie per lavorare con [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. Seleziona i campi che prevedi di ricevere dall’evento. Questi sono i campi che l’utente aziendale sfrutterà nel percorso. Devono inoltre includere la chiave che verrà utilizzata per identificare la persona associata all’evento (vedi [questa pagina](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Per gli eventi generati dal sistema, **[!UICONTROL eventID]** viene aggiunto automaticamente nell’elenco dei campi selezionati in modo che [!DNL Journey Orchestration] può identificare l’evento. Il sistema che trasmette l’evento non deve generare un ID, deve utilizzare quello disponibile nell’anteprima del payload. Consulta [questa pagina](../event/previewing-the-payload.md).

1. Dopo aver selezionato i campi necessari, fai clic su **[!UICONTROL Save]** o premere **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   Il numero di campi selezionati viene visualizzato nel **[!UICONTROL Payload]** campo.

   ![](../assets/journey12.png)
