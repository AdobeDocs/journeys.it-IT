---
title: 'Origine dati Adobe Experience Platform '
description: 'Scopri come configurare l’origine dati di Adobe Experience Platform '
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
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# Origine dati Adobe Experience Platform {#concept_zrb_nqt_52b}

L’origine dati di Experience Platform definisce la connessione a Real-time Customer Profile Service. Questa origine dati è incorporata e preconfigurata. Non può essere eliminato. Questa origine dati è progettata per recuperare e utilizzare i dati dal Servizio profili cliente in tempo reale (ad esempio, verificare se la persona che ha effettuato un viaggio è una donna). Consente di utilizzare i dati di profilo e gli eventi esperienza. Per ulteriori informazioni sul servizio Profilo cliente in tempo reale, consulta questa [pagina](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md).

>[!NOTE]
>
>Potete recuperare gli ultimi 1000 eventi di esperienza creati meno di un anno fa.

Per consentire la connessione al Servizio profili cliente in tempo reale, dobbiamo utilizzare una chiave per identificare una persona e uno spazio dei nomi che contestualizzi la chiave. Di conseguenza, è possibile utilizzare questa origine dati solo se i viaggi iniziano con un evento contenente una chiave e uno spazio dei nomi. Vedere [](../building-journeys/journey.md).

Potete modificare il gruppo di campi preconfigurato denominato &quot;ProfileFieldGroup&quot;, aggiungere nuovi e rimuovere quelli che non sono utilizzati in alcuna bozza o in viaggi live. Vedere [](../datasource/field-groups.md).

Di seguito sono riportati i passaggi principali per aggiungere gruppi di campi all&#39;origine dati incorporata.

1. Dall&#39;elenco delle origini dati, seleziona l&#39;origine dati integrata della piattaforma Experience.

   Viene aperto il riquadro di configurazione dell&#39;origine dati sul lato destro dello schermo.

   ![](../assets/journey23.png)

1. Fare clic **[!UICONTROL Add a New Field Group]**per definire una nuova serie di campi da recuperare. Vedere[](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Selezionare uno schema dal **[!UICONTROL Schema]**menu a discesa. In questo campo sono elencati gli schemi di eventi di profilo ed esperienza disponibili nella piattaforma. La creazione dello schema non viene eseguita nell&#39;orchestrazione del percorso. Viene eseguita nella piattaforma dati.
1. Selezionate i campi che desiderate usare.
1. Definite la durata della cache.
1. Fate clic su **[!UICONTROL Save]**.

Quando si posiziona il cursore sul nome di un gruppo di campi, vengono visualizzate due icone a destra. Consentono di eliminare e duplicare il gruppo di campi. L&#39; **[!UICONTROL Delete]**icona è disponibile solo se il gruppo di campi non è utilizzato in alcun viaggio live o in bozza (informazioni visualizzate nel**[!UICONTROL Used in]** campo).
