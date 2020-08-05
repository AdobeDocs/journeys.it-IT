---
title: Configurazione dell’origine dati
description: Scopri come configurare l’origine dati per il caso di utilizzo semplice del percorso
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 6%

---


# Configurazione dell’origine dati{#concept_ax3_bcy_w2b}

Nel nostro caso d&#39;uso, vogliamo utilizzare dati di personalizzazione per i nostri messaggi. Dobbiamo anche verificare se la persona è una donna. Queste informazioni sono memorizzate nel database del profilo cliente in tempo reale. L&#39;utente **** tecnico deve verificare che tali campi siano definiti nell&#39;origine dati Adobe Experience Platform incorporata.

Per ulteriori informazioni sulla configurazione dell&#39;origine dati, fare riferimento a [](../datasource/about-data-sources.md).

1. Nel menu principale, fare clic sulla **[!UICONTROL Data Sources]** scheda e selezionare l&#39;origine dati Adobe Experience Platform incorporata.

   ![](../assets/journey23.png)

1. Nei gruppi di campi, verificate che siano selezionati i campi seguenti:

   * _Persona > nome > firstName_
   * _persona > nome > lastName_
   * _persona > genere_
   * _personalEmail > address_

1. Fai clic su **[!UICONTROL Save]**.

L&#39;origine dati ora è configurata e pronta per essere utilizzata durante il viaggio.
