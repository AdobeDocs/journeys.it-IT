---
product: adobe campaign
title: Informazioni sulle origini dati
description: Informazioni su come configurare un’origine dati
feature: Journeys
role: User
level: Intermediate
exl-id: 2371d2c9-3035-46ac-9c76-755fb453c24e
source-git-commit: 4f6c5f9326b4d1cc4a1a02a036b51e4ad1ae68c4
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 80%

---

# Informazioni sulle origini dati {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Informazioni sulle origini dati"
>abstract="La configurazione dell’origine dati consente di definire una connessione a un sistema per il recupero di informazioni aggiuntive che verranno utilizzate nei percorsi."

La configurazione dell’origine dati consente di definire una connessione a un sistema per il recupero di informazioni aggiuntive, le quali verranno utilizzate nei percorsi e consentiranno di ottenere:

* [definizione della condizione](../building-journeys/condition-activity.md)
* Dati dei parametri e di personalizzazione nelle [azioni](../action/action.md).
* [definizione di attesa personalizzata](../building-journeys/wait-activity.md#custom)
* [definizione del fuso orario](../building-journeys/timezone-management.md)

Questa configurazione non è necessaria se i percorsi sfruttano solo i dati locali provenienti da un payload di eventi. Ad esempio, se il percorso è composto da un evento seguito da un’attività e-mail che utilizza solo i dati dell’evento, non è necessario configurare un’origine dati.

Esistono due tipi di origini dati:

* L’origine dati preconfigurata di Adobe Experience Platform che definisce la connessione al servizio Profilo del cliente in tempo reale, che costituisce un’origine dati incorporata. Consulta [questa pagina](../datasource/adobe-experience-platform-data-source.md).
* Le origini dati esterne che consentono di definire una connessione ai sistemi esterni, ovvero quelle che puoi creare. Consulta [questa pagina](../datasource/external-data-sources.md).

Per ciascuna origine dati è possibile definire le informazioni da recuperare utilizzando i gruppi di campi. I gruppi di campi costituiscono insiemi di campi che possono essere recuperati da un’origine dati. Consulta [questa pagina](../datasource/field-groups.md).

Di seguito sono riportati i passaggi principali per la configurazione dell’origine dati:

>[!NOTE]
>
>La configurazione dell’origine dati viene sempre eseguita da un **utente tecnico**.

1. Nel riquadro dei menu, selezionare **[!UICONTROL Admin]**. Nella sezione **[!UICONTROL Data sources]**, fare clic su **[!UICONTROL Manage]**.

   Viene visualizzato l’elenco delle origini dati. Per ulteriori informazioni sull&#39;interfaccia, vedere [questa pagina](../about/user-interface.md).

   ![](../assets/journey18.png)

1. Quindi puoi aggiungere gruppi di campi all&#39;origine dati incorporata (vedi [questa pagina](../datasource/adobe-experience-platform-data-source.md)) o creare una nuova origine dati esterna (vedi [questa pagina](../datasource/external-data-sources.md)) e i gruppi di campi associati (vedi [questa pagina](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Fai clic su **[!UICONTROL Save]**.

   Adesso l’origine dati è configurata ed è pronta per essere utilizzata nei percorsi.
