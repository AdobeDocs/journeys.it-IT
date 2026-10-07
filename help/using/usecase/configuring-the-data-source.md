---
product: adobe campaign
title: Configurazione dell’origine dati
description: Scopri come configurare l’origine dati per il caso d’uso semplice del percorso
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 31%
---
# Configurazione dell’origine dati{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._


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
