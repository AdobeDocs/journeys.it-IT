---
title: Informazioni sulle azioni
description: Informazioni su come configurare un’azione
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 89%

---


# Informazioni sulle azioni {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="Informazioni sulle azioni"
>abstract="In questa sezione è possibile definire la connessione al sistema che invierà i messaggi. Le azioni qui configurate saranno quindi disponibili nella palette a sinistra del percorso, nella categoria Azione. "

Le azioni rappresentano le connessioni attraverso le quali puoi offrire esperienze personalizzate in tempo reale ai clienti, ad esempio notifiche push, e-mail, SMS o qualsiasi altro strumento di coinvolgimento digitale che utilizzi nella tua azienda.

Le azioni personalizzate ti consentono di configurare la connessione di un sistema di terze parti in modo da consentire l’invio di messaggi o chiamate API. Per ciascun provider è possibile configurare un’azione che può essere attivata tramite un’API REST con un payload in formato JSON.

The actions are available in the left palette of your journey, in the **[!UICONTROL Action]** category. Consulta [questa pagina](../building-journeys/about-action-activities.md).

>[!NOTE]
>
>La configurazione delle azioni personalizzate viene sempre eseguita da un **utente tecnico**.

Nell’elenco **Azioni**, puoi premere c per creare un nuovo percorso, azione, origine dati o evento. For more information on shortcuts in [!DNL Journey Orchestration], see [this section](../about/user-interface.md#section_ksq_zr1_ffb).

Per visualizzare l’elenco delle azioni o configurarne una nuova, fai clic su **[!UICONTROL Actions]** nei menu principali. Viene visualizzato l’elenco delle azioni. See [this page](../about/user-interface.md) for more information on the interface.

![](../assets/custom1.png)

Se disponi di Adobe Campaign Standard, devi configurare l’azione predefinita affinché esegua l’invio di e-mail, notifiche push e SMS tramite le funzionalità di messaggistica transazionale di Adobe Campaign Standard. Consulta [questa pagina](../action/working-with-adobe-campaign.md).

Se utilizzi un sistema di terze parti per l’invio di messaggi come Epsilon, Facebook, Adobe.io, Firebase e così via, devi aggiungere e configurare un’azione personalizzata. Consulta [questa pagina](../action/about-custom-action-configuration.md).

Per ulteriori informazioni su come configurare un’azione per [!DNL Journey Orchestration] e in che modo utilizzarla in un percorso, guarda questo [tutorial video](https://docs.adobe.com/content/help/it-IT/journey-orchestration-learn/tutorials/configure-actions.html).
