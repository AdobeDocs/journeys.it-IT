---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sulle origini dati
description: 'Informazioni su come configurare un’origine dati '
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 88%

---


# Informazioni sulle origini dati {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Informazioni sulle origini dati"
>abstract="La configurazione dell’origine dati viene sempre eseguita da un utente tecnico. La configurazione dell’origine dati consente di definire una connessione a un sistema per il recupero di informazioni aggiuntive, le quali verranno utilizzate nei percorsi. Tali informazioni saranno destinate a: definizione della condizione, dati relativi a parametri e personalizzazione nelle azioni, definizione di attesa personalizzata, impostazione del fuso orario."

La configurazione dell’origine dati consente di definire una connessione a un sistema per il recupero di informazioni aggiuntive, le quali verranno utilizzate nei percorsi e consentiranno di ottenere:

* [Definizione della condizione.](../building-journeys/condition-activity.md)
* Dati dei parametri e di personalizzazione nelle [azioni](../action/action.md).
* [Impostazione di attesa personalizzata](../building-journeys/wait-activity.md#custom).
* [Impostazione del fuso orario](../building-journeys/timezone-management.md)

Questa configurazione non è necessaria se i percorsi sfruttano solo i dati locali provenienti da un payload di eventi. Ad esempio, se il percorso è composto da un evento seguito da un’attività e-mail che utilizza solo i dati dell’evento, non è necessario configurare un’origine dati.

Esistono due tipi di origini dati:

* L’origine dati preconfigurata di Adobe Experience Platform che definisce la connessione al servizio Profilo del cliente in tempo reale, che costituisce un’origine dati incorporata. Consulta [questa pagina](../datasource/adobe-experience-platform-data-source.md).
* Le origini dati esterne che consentono di definire una connessione ai sistemi esterni, ovvero quelle che puoi creare. Consulta [questa pagina](../datasource/external-data-sources.md).

Per ciascuna origine dati è possibile definire le informazioni da recuperare utilizzando i gruppi di campi. I gruppi di campi costituiscono insiemi di campi che possono essere recuperati da un’origine dati. Consulta [questa pagina](../datasource/field-groups.md).

Per ulteriori informazioni su come configurare un’origine dati di Adobe Experience Platform e un’origine dati esterna, nonché su come individuare e utilizzare i dati all’interno di un percorso, guarda questo [video di esercitazione](https://docs.adobe.com/content/help/it-IT/journey-orchestration-learn/tutorials/configure-data-sources.html).

Di seguito sono riportati i passaggi principali per la configurazione dell’origine dati:

>[!NOTE]
>
>La configurazione dell’origine dati viene sempre eseguita da un **utente tecnico**.

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Data Sources]**.

   Viene visualizzato l’elenco delle origini dati. See [this page](../about/user-interface.md) for more information on the interface.

   ![](../assets/journey18.png)

1. Then you can either add field groups to the built-in data source (see [this page](../datasource/adobe-experience-platform-data-source.md)) or create a new external data source (see [this page](../datasource/external-data-sources.md)) and associated field groups (see [this page](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Clic **[!UICONTROL Save]**.

   Adesso l’origine dati è configurata ed è pronta per essere utilizzata nei percorsi.
