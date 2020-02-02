---
title: Informazioni sulle origini dati
description: 'Informazioni su come configurare un''origine dati '
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
source-git-commit: d0a7bbb43ae62fbdcf7ef34b0b56b1d437047ad2

---


# Informazioni sulle origini dati {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id=&quot;jo_datasources&quot;
>title=&quot;Informazioni sulle origini dati&quot;
>abstract=&quot;La configurazione dell&#39;origine dati viene sempre eseguita da un utente tecnico. La configurazione dell&#39;origine dati consente di definire una connessione a un sistema per recuperare informazioni aggiuntive che verranno utilizzate nei viaggi, per: definizione della condizione, parametri e dati di personalizzazione in azioni, definizione di attesa personalizzata, definizione del fuso orario personalizzato.&quot;

La configurazione dell&#39;origine dati viene sempre eseguita da un utente **** tecnico.

La configurazione dell&#39;origine dati consente di definire una connessione a un sistema per recuperare informazioni aggiuntive che verranno utilizzate nei viaggi, per:

* definizione condizione
* dati relativi a parametri e personalizzazione in azioni
* definizione di attesa personalizzata
* definizione del fuso orario personalizzato

Questa configurazione non è necessaria se i viaggi sfruttano solo i dati locali provenienti da un payload di eventi. Ad esempio, se il viaggio è composto da un evento seguito da un&#39;attività e-mail che utilizza solo i dati dell&#39;evento, non è necessario configurare un&#39;origine dati.

Esistono due tipi di origini dati:

* L’origine dati preconfigurata della piattaforma Experience che definisce la connessione al servizio profili cliente in tempo reale. È un&#39;origine dati incorporata. Vedere [](../datasource/adobe-experience-platform-data-source.md).
* Le origini dati esterne che consentono di definire una connessione a sistemi esterni. Questi sono quelli che potete creare. Vedere [](../datasource/external-data-sources.md).

Per ogni origine dati è possibile definire le informazioni da recuperare utilizzando i gruppi di campi. Vedere [](../datasource/field-groups.md).

Di seguito sono riportati i passaggi principali per la configurazione dell&#39;origine dati:

1. Nel menu principale, fate clic sulla **[!UICONTROL Data Sources]**scheda.

   Viene visualizzato l&#39;elenco delle origini dati. Consultate [](../about/user-interface.md) per ulteriori informazioni sull&#39;interfaccia.

   ![](../assets/journey18.png)

1. È quindi possibile aggiungere gruppi di campi all&#39;origine dati incorporata (vedere [](../datasource/adobe-experience-platform-data-source.md)) o creare una nuova origine dati esterna (vedere [](../datasource/external-data-sources.md)) e i gruppi di campi associati (vedere [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Clic **[!UICONTROL Save]**.

   L&#39;origine dati ora è configurata e pronta per essere utilizzata nei viaggi.
