---
title: Sfruttare i punteggi di fatica
description: Scopri come sfruttare i punteggi di fatica nei viaggi
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Sfruttare i punteggi di fatica {#concept_dsh_1ry_wfb}

Questo caso di utilizzo vi mostrerà come sfruttare i punteggi di affaticamento per evitare di richiedere troppo ai vostri clienti nei vostri viaggi.

>[!CAUTION]
>
>La funzionalità di valutazione della fatica predittiva è disponibile solo per i clienti che utilizzano la funzione Adobe Campaign Standard Data Service.

## Configurazione dell’evento {#section_ptb_ws1_ffb}

Seguite i passaggi descritti in [](../event/about-events.md).

## Configurazione dell&#39;origine dati {#section_o3n_4yy_wfb}

Per selezionare i campi del punteggio di affaticamento nell&#39;origine dati incorporata, effettuare le operazioni seguenti:

1. Nel menu principale, fate clic sulla **[!UICONTROL Data Sources]**scheda e selezionate l&#39;origine dati integrata della piattaforma Experience.

   ![](../assets/journey23.png)

1. Verificate che i campi richiesti per il caso di utilizzo siano selezionati.
1. Fai clic **[!UICONTROL Add a New Field Group]**, seleziona il**[!UICONTROL Profiles]** modello e aggiungi i **[!UICONTROL fatigueLevel]**campi e (in**[!UICONTROL fatigueScore]** viaggioAI > emailScore > fatica __).

   ![](../assets/journeyuc3_1.png)

1. Clic **[!UICONTROL Save]**.

## Costruire il viaggio {#section_uzm_pyy_wfb}

Per creare, convalidare e pubblicare il percorso, segui i passaggi descritti in [](../building-journeys/journey.md).

Nel nostro caso d&#39;uso, stiamo sfruttando il **[!UICONTROL fatigueLevel]**campo. È inoltre possibile utilizzare il**[!UICONTROL fatigueScore]** campo.

Per sfruttare il livello di affaticamento del percorso, effettua i seguenti passaggi:

1. Aggiungete un evento e una condizione al vostro viaggio.

   ![](../assets/journeyuc2_14.png)

1. Scegliete il **[!UICONTROL Data Source Condition]**tipo e fate clic nel**[!UICONTROL Expression]** campo.

   ![](../assets/journeyuc3_2.png)

1. Utilizzando l&#39;editor di espressioni semplici, cerca il **[!UICONTROL fatigueLevel]**campo (_ExperiencePlatformDataSource > JourneyAIScores > Profile > pathAI > emailScore > fatigue_), rilascialo a destra e crea la seguente condizione: &quot;fatigueLevel è uguale a &quot;Low&quot;. Clic**[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   L&#39;espressione avanzata è:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. Nella condizione, creare altri due percorsi per livelli di affaticamento medio e alto.

   ![](../assets/journeyuc3_4.png)

1. Ora potete aggiungere diverse azioni per ogni livello di affaticamento.

   ![](../assets/journeyuc3_5.png)
