---
product: adobe campaign
title: Sfruttare i punteggi di fatica
description: Scopri come sfruttare i punteggi di affaticamento nei percorsi
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 10%

---


# Sfruttamento dell’intelligenza artificiale del percorso {#concept_dsh_1ry_wfb}

Questo caso d’uso ti mostrerà come sfruttare i punteggi di affaticamento per evitare di richiedere troppo ai tuoi clienti nei tuoi percorsi.

>[!NOTE]
>
>La funzionalità Punteggio di affaticamento predittivo è disponibile solo per i clienti che utilizzano il [Connettore dati Adobe Experience Platform](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).

## Configurazione dell’evento {#section_ptb_ws1_ffb}

Segui i passaggi descritti in [questa pagina](../event/about-events.md).

## Configurazione dell’origine dati {#section_o3n_4yy_wfb}

Esegui i seguenti passaggi per selezionare i campi del punteggio di affaticamento nell’origine dati incorporata:

1. Nel riquadro del menu, selezionare **[!UICONTROL Admin]**. Nella sezione **[!UICONTROL Data sources]**, fai clic su **[!UICONTROL Manage]**.
1. Seleziona l’origine dati integrata di Adobe Experience Platform.

   ![](../assets/journey23.png)

1. Verifica che siano selezionati i campi richiesti per il tuo caso d’uso.
1. Fai clic su **[!UICONTROL Add a New Field Group]**, seleziona il modello **[!UICONTROL Profiles]** e aggiungi i campi **[!UICONTROL fatigueLevel]** e **[!UICONTROL fatigueScore]** (in _journeyAI > emailScore > fatigue_).

   ![](../assets/journeyuc3_1.png)

1. Fai clic su **[!UICONTROL Save]**.

## Creazione di un percorso {#section_uzm_pyy_wfb}

Per creare, convalidare e pubblicare il percorso, segui i passaggi descritti in [questa pagina](../building-journeys/journey.md).

Nel nostro caso d’uso, sfruttiamo il campo **[!UICONTROL fatigueLevel]** . Puoi inoltre utilizzare il campo **[!UICONTROL fatigueScore]** .

Esegui i seguenti passaggi per sfruttare il livello di affaticamento nel percorso:

1. Aggiungi un evento e una condizione nel percorso.

   ![](../assets/journeyuc2_14.png)

1. Scegli il tipo di **[!UICONTROL Data Source Condition]** e fai clic nel campo **[!UICONTROL Expression]**. 

   ![](../assets/journeyuc3_2.png)

1. Utilizzando l’editor di espressioni semplici, cerca il campo **[!UICONTROL fatigueLevel]** (_ExperiencePlatformDataSource > JourneyAIScores > Profilo > journeyAI > emailScore > fatigue_), rilascialo a destra e crea la seguente condizione: &quot;fatigueLevel è uguale a &quot;Low&quot;. Fai clic su **[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   L&#39;espressione avanzata è:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. Nella condizione , crea altri due percorsi per livelli di affaticamento medi e alti.

   ![](../assets/journeyuc3_4.png)

1. Ora puoi aggiungere diverse azioni per ogni livello di affaticamento.

   ![](../assets/journeyuc3_5.png)
