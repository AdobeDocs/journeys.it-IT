---
product: adobe campaign
title: Informazioni sulle azioni
description: Informazioni su come configurare un’azione
feature: Journeys
role: User
level: Intermediate
exl-id: 34f7666b-1c91-4edd-b5d6-4c0513b9c4f3
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 84%

---

# Informazioni sulle azioni {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="Informazioni sulle azioni"
>abstract="In questa sezione è possibile definire la connessione al sistema che invierà i messaggi. Le azioni qui configurate saranno quindi disponibili nella palette a sinistra del percorso, nella categoria Azione. "

Le azioni rappresentano le connessioni attraverso le quali puoi offrire esperienze personalizzate in tempo reale ai clienti, ad esempio notifiche push, e-mail, SMS o qualsiasi altro strumento di coinvolgimento digitale che utilizzi nella tua azienda.

Le azioni personalizzate consentono di configurare la connessione di un sistema di terze parti per consentire l’invio di messaggi o chiamate API. Per ciascun provider è possibile configurare un’azione che può essere attivata tramite un’API REST con un payload in formato JSON.

Le azioni sono disponibili nella palette a sinistra del percorso, nella categoria **[!UICONTROL Action]**. Consulta [questa pagina](../building-journeys/about-action-activities.md).

>[!NOTE]
>
>La configurazione delle azioni personalizzate viene sempre eseguita da un **utente tecnico**.

Nell’elenco **Azioni**, puoi premere c per creare un nuovo percorso, azione, origine dati o evento. Per ulteriori informazioni sui collegamenti in [!DNL Journey Orchestration], vedere [questa sezione](../about/user-interface.md#section_ksq_zr1_ffb).

Per visualizzare l’elenco delle azioni o configurarne una nuova, fai clic su **[!UICONTROL Actions]** nei menu principali. Viene visualizzato l’elenco delle azioni. Per ulteriori informazioni sull&#39;interfaccia, vedere [questa pagina](../about/user-interface.md).

![](../assets/custom1.png)

Se disponi di Adobe Campaign Standard, devi configurare l’azione predefinita affinché esegua l’invio di e-mail, notifiche push e SMS tramite le funzionalità di messaggistica transazionale di Adobe Campaign Standard. Consulta [questa pagina](../action/working-with-adobe-campaign.md).

Se disponi di Adobe Campaign v7 o v8, su richiesta è disponibile un’integrazione. Consulta [questa pagina](../action/acc-action.md).

Se utilizzi un sistema di terze parti per l’invio di messaggi come Epsilon, Facebook, Adobe.io, Firebase e così via, devi aggiungere e configurare un’azione personalizzata. Consulta [questa pagina](../action/about-custom-action-configuration.md).

Per ulteriori informazioni su come configurare un’azione per [!DNL Journey Orchestration] e in che modo utilizzarla in un percorso, guarda questo [tutorial video](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/configure-actions.html).
