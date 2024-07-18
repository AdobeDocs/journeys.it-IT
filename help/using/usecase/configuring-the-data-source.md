---
product: adobe campaign
title: Configurazione dell’origine dati
description: Scopri come configurare l’origine dati per il caso d’uso semplice del percorso
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 6%

---

# Configurazione dell’origine dati{#concept_ax3_bcy_w2b}

Nel nostro caso d’uso, vogliamo utilizzare i dati di personalizzazione per i nostri messaggi. Dobbiamo anche verificare se la persona è una donna. Queste informazioni vengono memorizzate nel database Profilo cliente in tempo reale. L&#39;**utente tecnico** deve verificare che tali campi siano definiti nell&#39;origine dati integrata di Adobe Experience Platform.

Per ulteriori informazioni sulla configurazione dell&#39;origine dati, consultare [questa pagina](../datasource/about-data-sources.md).

1. Nel riquadro dei menu, selezionare **[!UICONTROL Admin]**. Nella sezione **[!UICONTROL Data sources]**, fare clic su **[!UICONTROL Manage]**.
1. Seleziona l’origine dati integrata di Adobe Experience Platform.

   ![](../assets/journey23.png)

1. Nei gruppi di campi, verifica che siano selezionati i campi seguenti:

   * _persona > nome > nome_
   * _persona > nome > cognome_
   * _persona > genere_
   * _e-mail personale > indirizzo_

1. Fai clic su **[!UICONTROL Save]**.

L’origine dati è ora configurata ed è pronta per essere utilizzata nel percorso.
