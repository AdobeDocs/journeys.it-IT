---
product: adobe campaign
title: Origine dati Adobe Experience Platform
description: Scopri come configurare l’origine dati Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 25%
---
# Origine dati Adobe Experience Platform {#concept_zrb_nqt_52b}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._


L’origine dati Adobe Experience Platform definisce la connessione al servizio Profilo cliente in tempo reale. Questa origine dati è incorporata e preconfigurata. Non può essere cancellato. Questa origine dati è progettata per recuperare e utilizzare i dati del servizio Profilo cliente in tempo reale (ad esempio, verificare se la persona che ha inserito un percorso è una donna). Consente di utilizzare i dati del profilo e i dati di eventi esperienza. Per ulteriori informazioni sul servizio Profilo cliente in tempo reale, consulta questa [pagina](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it).

>[!NOTE]
>
>Puoi recuperare i 1000 eventi di esperienza più recenti creati meno di un anno fa.

Per consentire la connessione al servizio Profilo cliente in tempo reale, è necessario utilizzare una chiave per identificare una persona e uno spazio dei nomi che la contestualizza. Di conseguenza, puoi utilizzare questa origine dati solo se i tuoi percorsi iniziano con un evento contenente una chiave e uno spazio dei nomi. Consulta [questa pagina](../building-journeys/journey.md).

Puoi modificare il gruppo di campi preconfigurato denominato &quot;ProfileFieldGroup&quot;, aggiungerne di nuovi e rimuovere quelli che non sono utilizzati in alcun percorso in bozza o live. Consulta [questa pagina](../datasource/field-groups.md).

Di seguito sono riportati i passaggi principali per aggiungere gruppi di campi all’origine dati incorporata.

1. Dall’elenco delle origini dati, seleziona l’origine dati integrata di Adobe Experience Platform.

   Sul lato destro dello schermo si apre il riquadro di configurazione dell’origine dati .

   ![](../assets/journey23.png)

1. Fare clic su **[!UICONTROL Add a New Field Group]** per definire una nuova serie di campi da recuperare. Consulta [questa pagina](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Selezionare uno schema dal menu a discesa **[!UICONTROL Schema]**. Questo campo elenca gli schemi Profilo ed Eventi esperienza disponibili in Adobe Experience Platform. Creazione dello schema non eseguita in [!DNL Journey Orchestration]. Viene eseguito nel Adobe Experience Platform.
1. Selezionare i campi da utilizzare.
1. Fai clic su **[!UICONTROL Save]**.

Quando si posiziona il cursore sul nome di un gruppo di campi, a destra vengono visualizzate due icone. Ti consentono di eliminare e duplicare il gruppo di campi. L&#39;icona **[!UICONTROL Delete]** è disponibile solo se il gruppo di campi non è utilizzato in alcun percorso live o in bozza (informazioni visualizzate nel campo **[!UICONTROL Used in]**).
