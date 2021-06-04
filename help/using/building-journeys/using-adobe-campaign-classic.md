---
product: adobe campaign
solution: Journey Orchestration
title: Utilizzo delle azioni di Adobe Campaign
description: Informazioni sulle azioni di Adobe Campaign
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: b108294acf8e1c4be00ca981e7ba15a23973f8ac
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 3%

---

# Utilizzo di Adobe Campaign Classic {#using_campaign_classic}

Se disponi di Adobe Campaign Classic, è disponibile un’integrazione . Ti consentirà di inviare e-mail, notifiche push e SMS utilizzando le funzionalità di messaggistica transazionale di Adobe Campaign Classic.

La connessione tra le istanze Journey Orchestration e Campaign Classic viene impostata per Adobe al momento del provisioning. Adobe di contatto.

Affinché questo funzioni, devi configurare un’azione dedicata. Fare riferimento a questa sezione [sezione](../action/acc-action.md).

In questa [sezione](../usecase/campaign-classic-use-case.md) viene presentato un caso d’uso end-to-end.

1. Progetta il tuo percorso, a partire da un evento. Vedere questa sezione [](../building-journeys/journey.md).
1. Nella sezione **Azione** della palette, seleziona un’azione Campaign Classic e aggiungilo al percorso.
1. Nei **Parametri azione** vengono visualizzati tutti i campi previsti nel payload del messaggio. Devi mappare ciascuno di questi campi con il campo che desideri utilizzare, dall’evento o dall’origine dati. È simile alle azioni personalizzate. Fare riferimento a questa sezione [sezione](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
