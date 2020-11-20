---
product: adobe campaign
solution: Journey Orchestration
title: Introduzione
description: Scopri i passaggi principali per configurare Journey Orchestration e creare il primo percorso.
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 92%

---


# Introduzione{#concept_y4b_4qt_52b}

In [!DNL Journey Orchestration], esistono due tipi di utenti, ciascuno dei quali esegue attività specifiche: l’**utente tecnico** e l’**utente aziendale**. L’accesso dell’utente viene gestito tramite profili di prodotto e diritti. Refer to [this page](../about/access-management.md) to learn how to configure user access.

Di seguito sono riportati i passaggi principali per la configurazione e l’utilizzo di [!DNL Journey Orchestration]:

1. **Configurare un evento**

   È necessario definire le informazioni previste e le modalità con cui elaborarle. Questa configurazione è obbligatoria e viene eseguita da un **utente tecnico**.

   Per ulteriori informazioni, consulta [questa pagina](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Configurare l’origine dati**

   È necessario definire una connessione a un sistema per il recupero di informazioni aggiuntive che verranno utilizzate nei percorsi, ad esempio all’interno delle tue condizioni. Al momento del provisioning, viene configurata anche un’origine dati integrata in Adobe Experience Platform. Se sfrutti solo i dati degli eventi del tuo percorso, questo passaggio non è necessario e viene eseguito da un **utente tecnico**.

   Per ulteriori informazioni, consulta [questa pagina](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Configurare un’azione**

   Se utilizzi un sistema di terze parti per l’invio dei messaggi, è necessario configurare la relativa connessione con [!DNL Journey Orchestration]. Consulta [questa pagina](../action/about-custom-action-configuration.md).

   Se utilizzi Adobe Campaign Standard per l’invio dei messaggi, è necessario configurare l’azione incorporata. Consulta [questa pagina](../action/working-with-adobe-campaign.md).

   Questi passaggi vengono eseguiti da un **utente tecnico**.

   ![](../assets/custom2.png)

1. **Progettazione del percorso**

   Combina le diverse attività relative a un evento, un percorso e un’azione in modo da creare scenari tra canali con più passaggi. Questo passaggio viene eseguito da un **utente aziendale**.

   Per ulteriori informazioni, consulta [questa pagina](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Test e pubblicazione del percorso**

   È necessario convalidare e attivare il percorso. Questo passaggio viene eseguito da un **utente aziendale**.

   Per ulteriori informazioni, consulta le pagine [Test del percorso](../building-journeys/testing-the-journey.md) e [Pubblicazione del percorso](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Monitorare il percorso**

   Per misurare l’efficacia del percorso, utilizza gli strumenti di reporting dedicati. Questo passaggio viene eseguito da un **utente aziendale**.

   Per ulteriori informazioni, consulta [questa pagina](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

