---
product: adobe campaign
title: 'Origine dati Adobe Experience Platform '
description: 'Scopri come configurare l’origine dati Adobe Experience Platform '
feature: Journeys
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 11%

---

# Origine dati Adobe Experience Platform {#concept_zrb_nqt_52b}

L’origine dati Adobe Experience Platform definisce la connessione al servizio Profilo cliente in tempo reale. Questa origine dati è incorporata e preconfigurata. Non può essere eliminato. Questa origine dati è progettata per recuperare e utilizzare i dati dal servizio Profilo cliente in tempo reale (ad esempio, controlla se la persona che ha inserito un percorso è una donna). Ti consente di utilizzare i dati Profilo e i dati Eventi esperienza. Per ulteriori informazioni sul servizio Profilo cliente in tempo reale, consulta questo [page](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it).

>[!NOTE]
>
>Puoi recuperare gli ultimi 1000 eventi di esperienza creati meno di un anno fa.

Per consentire la connessione al servizio Profilo cliente in tempo reale, è necessario utilizzare una chiave per identificare una persona e uno spazio dei nomi che contestualizza la chiave. Di conseguenza, puoi utilizzare questa origine dati solo se i percorsi iniziano con un evento contenente una chiave e uno spazio dei nomi. Consulta [questa pagina](../building-journeys/journey.md).

È possibile modificare il gruppo di campi preconfigurato denominato &quot;ProfileFieldGroup&quot;, aggiungerne di nuovi e rimuovere quelli che non sono utilizzati in alcuna bozza o percorso live. Consulta [questa pagina](../datasource/field-groups.md).

Di seguito sono riportati i passaggi principali per aggiungere gruppi di campi all’origine dati incorporata.

1. Dall’elenco delle origini dati, selezionare l’origine dati integrata di Adobe Experience Platform.

   Sul lato destro dello schermo si apre il riquadro di configurazione dell’origine dati .

   ![](../assets/journey23.png)

1. Fai clic su **[!UICONTROL Add a New Field Group]** definire una nuova serie di campi da recuperare. Consulta [questa pagina](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Seleziona uno schema dal **[!UICONTROL Schema]** a discesa. In questo campo sono elencati gli schemi di profili ed eventi di esperienza disponibili in Adobe Experience Platform. La creazione dello schema non viene eseguita in [!DNL Journey Orchestration]. Viene eseguito in Adobe Experience Platform.
1. Selezionare i campi da utilizzare.
1. Fai clic su **[!UICONTROL Save]**.

Quando si posiziona il cursore sul nome di un gruppo di campi, vengono visualizzate due icone a destra. Consentono di eliminare e duplicare il gruppo di campi. Tieni presente che **[!UICONTROL Delete]** l’icona è disponibile solo se il gruppo di campi non è utilizzato in alcun percorso live o di bozza (informazioni visualizzate nel **[!UICONTROL Used in]** (campo).
