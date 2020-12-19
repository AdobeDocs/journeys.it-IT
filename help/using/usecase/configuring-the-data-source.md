---
product: adobe campaign
solution: Journey Orchestration
title: Configurazione dell’origine dati
description: Scopri come configurare l’origine dati per il caso di utilizzo semplice del percorso
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Configurazione dell’origine dati{#concept_ax3_bcy_w2b}

Nel nostro caso d&#39;uso, vogliamo utilizzare dati di personalizzazione per i nostri messaggi. Dobbiamo anche verificare se la persona è una donna. Queste informazioni sono memorizzate nel database del profilo cliente in tempo reale. L&#39; **utente tecnico** deve verificare che tali campi siano definiti nell&#39;origine dati Adobe Experience Platform incorporata.

Per ulteriori informazioni sulla configurazione dell&#39;origine dati, fare riferimento a [questa pagina](../datasource/about-data-sources.md).

1. Nel menu principale, fare clic sulla scheda **[!UICONTROL Data Sources]** e selezionare l&#39;origine dati Adobe Experience Platform incorporata.

   ![](../assets/journey23.png)

1. Nei gruppi di campi, verificate che siano selezionati i campi seguenti:

   * _Persona > nome > firstName_
   * _persona > nome > lastName_
   * _persona > genere_
   * _personalEmail > address_

1. Fai clic su **[!UICONTROL Save]**.

L&#39;origine dati ora è configurata e pronta per essere utilizzata durante il viaggio.
