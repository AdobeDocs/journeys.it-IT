---
title: Informazioni sulle origini dati
description: 'Informazioni su come configurare un’origine dati '
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
source-git-commit: 1ccf020a882c1d6d9bd00f2e9f5d6b2aee6f7829
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 88%

---


# Informazioni sulle origini dati {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Informazioni sulle origini dati"
>abstract="La configurazione dell’origine dati viene sempre eseguita da un utente tecnico. La configurazione dell&#39;origine dati consente di definire una connessione a un sistema per recuperare informazioni aggiuntive che verranno utilizzate nei viaggi, per: definizione della condizione, parametri e dati di personalizzazione nelle azioni, definizione personalizzata del fuso orario, definizione del fuso orario."

La configurazione dell’origine dati consente di definire una connessione a un sistema per il recupero di informazioni aggiuntive, le quali verranno utilizzate nei percorsi e consentiranno di ottenere:

* [Definizione della condizione.](../building-journeys/condition-activity.md)
* Dati dei parametri e di personalizzazione nelle [azioni](../action/action.md).
* [Impostazione di attesa personalizzata](../building-journeys/wait-activity.md#custom).
* [definizione del fuso orario](../building-journeys/timezone-management.md)

Questa configurazione non è necessaria se i percorsi sfruttano solo i dati locali provenienti da un payload di eventi. Ad esempio, se il percorso è composto da un evento seguito da un’attività e-mail che utilizza solo i dati dell’evento, non è necessario configurare un’origine dati.

Esistono due tipi di origini dati:

* L’origine dati preconfigurata di Experience Platform che definisce la connessione al servizio Profilo del cliente in tempo reale, che costituisce un’origine dati incorporata. A questo proposito, consulta la sezione [](../datasource/adobe-experience-platform-data-source.md).
* Le origini dati esterne che consentono di definire una connessione ai sistemi esterni, ovvero quelle che puoi creare. A questo proposito, consulta la sezione [](../datasource/external-data-sources.md).

Per ciascuna origine dati è possibile definire le informazioni da recuperare utilizzando i gruppi di campi. I gruppi di campi costituiscono insiemi di campi che possono essere recuperati da un’origine dati. A questo proposito, consulta la sezione [](../datasource/field-groups.md).

Per ulteriori informazioni su come configurare un’origine dati Experience Platform ed esterna, nonché su come individuare e utilizzare i dati all’interno di un percorso, guarda questo [video di esercitazione](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-data-sources.html).

Di seguito sono riportati i passaggi principali per la configurazione dell’origine dati:

>[!NOTE]
>
>La configurazione dell’origine dati viene sempre eseguita da un **utente tecnico**.

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Data Sources]**.

   Viene visualizzato l’elenco delle origini dati. Per ulteriori informazioni sull’interfaccia, consulta la sezione [](../about/user-interface.md).

   ![](../assets/journey18.png)

1. È quindi possibile aggiungere gruppi di campi all’origine dati incorporata (consulta la sezione [](../datasource/adobe-experience-platform-data-source.md)) o creare una nuova origine dati esterna (vedi [](../datasource/external-data-sources.md)) e i gruppi di campi associati (consulta la sezione [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Clic **[!UICONTROL Save]**.

   Adesso l’origine dati è configurata ed è pronta per essere utilizzata nei percorsi.
