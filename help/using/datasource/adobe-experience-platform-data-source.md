---
product: adobe campaign
solution: Journey Orchestration
title: 'Origine dati Adobe Experience Platform '
description: 'Informazioni su come configurare l''origine dati Adobe Experience Platform '
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 11%

---


# Origine dati Adobe Experience Platform {#concept_zrb_nqt_52b}

L&#39;origine dati Adobe Experience Platform definisce la connessione a Real-time Customer Profile Service. Questa origine dati è incorporata e preconfigurata. Non può essere eliminato. Questa origine dati è progettata per recuperare e utilizzare i dati dal Servizio profili cliente in tempo reale (ad esempio, verificare se la persona che ha effettuato un viaggio è una donna). Consente di utilizzare i dati di profilo e gli eventi esperienza. Per ulteriori informazioni sul servizio Profilo cliente in tempo reale, consulta questa [pagina](https://docs.adobe.com/content/help/it-IT/experience-platform/profile/home.html).

>[!NOTE]
>
>Potete recuperare gli ultimi 1000 eventi di esperienza creati meno di un anno fa.

Per consentire la connessione al Servizio profili cliente in tempo reale, dobbiamo utilizzare una chiave per identificare una persona e uno spazio dei nomi che contestualizzi la chiave. Di conseguenza, è possibile utilizzare questa origine dati solo se i viaggi iniziano con un evento contenente una chiave e uno spazio dei nomi. Consulta [questa pagina](../building-journeys/journey.md).

Potete modificare il gruppo di campi preconfigurato denominato &quot;ProfileFieldGroup&quot;, aggiungere nuovi e rimuovere quelli che non sono utilizzati in alcuna bozza o in viaggi live. Consulta [questa pagina](../datasource/field-groups.md).

Di seguito sono riportati i passaggi principali per aggiungere gruppi di campi all&#39;origine dati incorporata.

1. Dall&#39;elenco delle origini dati, selezionare l&#39;origine dati Adobe Experience Platform incorporata.

   Sul lato destro dello schermo si apre il riquadro di configurazione dell’origine dati .

   ![](../assets/journey23.png)

1. Fare clic **[!UICONTROL Add a New Field Group]** per definire una nuova serie di campi da recuperare. Consulta [questa pagina](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Selezionare uno schema dal **[!UICONTROL Schema]** menu a discesa. In questo campo sono elencati gli schemi di eventi di profilo ed esperienza disponibili in Adobe Experience Platform. La creazione dello schema non viene eseguita in [!DNL Journey Orchestration]. Viene eseguito in Adobe Experience Platform.
1. Selezionate i campi che desiderate usare.
1. Definite la durata della cache.
1. Fate clic su **[!UICONTROL Save]**.

Quando si posiziona il cursore sul nome di un gruppo di campi, vengono visualizzate due icone a destra. Consentono di eliminare e duplicare il gruppo di campi. L&#39; **[!UICONTROL Delete]** icona è disponibile solo se il gruppo di campi non è utilizzato in alcun viaggio live o in bozza (informazioni visualizzate nel **[!UICONTROL Used in]** campo).
