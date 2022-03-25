---
product: adobe campaign
solution: Journey Orchestration
title: Utilizzo delle azioni Adobe Campaign v7/v8
description: Scopri le azioni di Adobe Campaign v7/v8
feature: Journeys
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 12%

---

# Utilizzo di Adobe Campaign v7/v8 {#using_campaign_classic}

È disponibile un’integrazione se disponi di Adobe Campaign v7 o v8. Ti consentirà di inviare e-mail, notifiche push e SMS utilizzando le funzionalità di messaggistica transazionale di Adobe Campaign.

La connessione tra le istanze Journey Orchestration e Campaign viene impostata per Adobe al momento del provisioning. Adobe di contatto.

Affinché questo funzioni, devi configurare un’azione dedicata. Fai riferimento a questo [sezione](../action/acc-action.md).

In questo viene presentato un caso d’uso end-to-end [sezione](../usecase/campaign-classic-use-case.md).

1. Progetta il tuo percorso, a partire da un evento. Vedi questo [sezione](../building-journeys/journey.md).
1. In **Azione** nella sezione della palette, seleziona un’azione Campaign e aggiungilo al percorso.
1. In **Parametri azione**, vengono visualizzati tutti i campi previsti nel payload del messaggio. Devi mappare ciascuno di questi campi con il campo che desideri utilizzare, dall’evento o dall’origine dati. È simile alle azioni personalizzate. Fai riferimento a questo [sezione](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
