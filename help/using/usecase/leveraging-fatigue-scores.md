---
product: adobe campaign
title: Sfruttare i punteggi di fatica
description: Scopri come sfruttare i punteggi di fatica in percorsi
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 12%

---


# Sfruttamento dell’intelligenza artificiale del percorso {#concept_dsh_1ry_wfb}

Questo caso d’uso ti mostrerà come sfruttare i punteggi di fatica per evitare di sollecitare eccessivamente i clienti nei tuoi percorsi.

>[!NOTE]
>
>La funzionalità del punteggio di fatica predittivo è disponibile solo per i clienti che utilizzano [Connettore dati Adobe Experience Platform](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).

## Configurazione dell’evento {#section_ptb_ws1_ffb}

Segui i passaggi descritti in [questa pagina](../event/about-events.md).

## Configurazione dell’origine dati {#section_o3n_4yy_wfb}

Per selezionare i campi del punteggio di affaticamento nell’origine dati incorporata, effettua le seguenti operazioni:

1. Nel riquadro del menu, seleziona **[!UICONTROL Admin]**. Dalla sezione **[!UICONTROL Data sources]**, fai clic su **[!UICONTROL Manage]**.
1. Seleziona l’origine dati integrata di Adobe Experience Platform.

   ![](../assets/journey23.png)

1. Verifica che i campi richiesti per il caso d’uso siano selezionati.
1. Clic **[!UICONTROL Add a New Field Group]**, seleziona la **[!UICONTROL Profiles]** e aggiungi **[!UICONTROL fatigueLevel]** e **[!UICONTROL fatigueScore]** campi (sotto _journeyAI > emailScore > fatigue_).

   ![](../assets/journeyuc3_1.png)

1. Fai clic su **[!UICONTROL Save]**.

## Creazione di un percorso {#section_uzm_pyy_wfb}

Per creare, convalidare e pubblicare il percorso, segui i passaggi descritti in [questa pagina](../building-journeys/journey.md).

Nel nostro caso d’uso, stiamo sfruttando **[!UICONTROL fatigueLevel]** campo. È inoltre possibile utilizzare **[!UICONTROL fatigueScore]** campo.

Per sfruttare il livello di affaticamento nel percorso, effettua le seguenti operazioni:

1. Aggiungi un evento e una condizione nel percorso.

   ![](../assets/journeyuc2_14.png)

1. Scegli il tipo di **[!UICONTROL Data Source Condition]** e fai clic nel campo **[!UICONTROL Expression]**. 

   ![](../assets/journeyuc3_2.png)

1. Utilizzando l’editor di espressioni semplici, cerca **[!UICONTROL fatigueLevel]** campo (_ExperiencePlatformDataSource > JourneyAIScores > Profilo > journeyAI > emailScore > fatigue_), rilasciarlo a destra e creare la seguente condizione: &quot;fatigueLevel is equal to &quot;Low&quot;. Fai clic su **[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   L’espressione avanzata è:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. Nella condizione, creare altri due percorsi per livelli di affaticamento medi e alti.

   ![](../assets/journeyuc3_4.png)

1. Ora puoi aggiungere diverse azioni per ogni livello di affaticamento.

   ![](../assets/journeyuc3_5.png)
