---
title: Guida introduttiva
description: Guida introduttiva all'orchestrazione del percorso
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Guida introduttiva{#concept_y4b_4qt_52b}

Nell&#39;orchestrazione del viaggio, esistono due tipi di utenti, ciascuno dei quali esegue attività specifiche: l&#39;utente **** tecnico e l&#39;utente **** aziendale. L&#39;accesso dell&#39;utente viene gestito tramite profili di prodotto e diritti. Fare riferimento [](../about/access-management.md) per apprendere come configurare l&#39;accesso utente.

Di seguito sono riportati i passaggi principali per configurare e utilizzare l&#39;orchestrazione del percorso:

1. **Configurare un evento**

   È necessario definire le informazioni previste e come elaborarle. Questa configurazione è obbligatoria. Questo passaggio viene eseguito da un utente **** tecnico.

   Per ulteriori informazioni, consulta [](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Configurare l&#39;origine dati**

   È necessario definire una connessione a un sistema per recuperare informazioni aggiuntive che verranno utilizzate nei viaggi, ad esempio nelle condizioni dell&#39;utente. Anche un&#39;origine dati integrata della piattaforma Experience è configurata al momento del provisioning. Questo passaggio non è richiesto se sfrutti solo i dati degli eventi del tuo viaggio. Questo passaggio viene eseguito da un utente **** tecnico.

   Per ulteriori informazioni, consulta [](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Configurare un&#39;azione**

   Se utilizzi un sistema di terze parti per inviare i messaggi, devi configurare la relativa connessione con l&#39;orchestrazione del percorso. Vedere [](../action/about-custom-action-configuration.md).

   Se utilizzi Adobe Campaign Standard per inviare messaggi, devi configurare l&#39;azione incorporata. Vedere [](../action/working-with-adobe-campaign.md).

   Questi passaggi vengono eseguiti da un utente **** tecnico.

   ![](../assets/custom2.png)

1. **Progettazione del viaggio**

   Combinate le diverse attività di evento, orchestrazione e azione per creare scenari multicanale con più passaggi. Questo passaggio viene eseguito da un utente **** aziendale.

   Per ulteriori informazioni, consulta [](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Test e pubblicazione del percorso**

   È necessario convalidare e attivare il percorso. Questo passaggio viene eseguito da un utente **** aziendale.

   Per ulteriori informazioni, consulta [](../building-journeys/testing-the-journey.md) e [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Monitorare il viaggio**

   Utilizzate gli strumenti di reporting dedicati per misurare l&#39;efficacia del viaggio. Questo passaggio viene eseguito da un utente **** aziendale.

   Per ulteriori informazioni, consulta [](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

