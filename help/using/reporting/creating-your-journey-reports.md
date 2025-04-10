---
product: adobe campaign
title: Creazione dei rapporti sui percorsi
description: Scopri come creare i rapporti sui percorsi
feature: Journeys
role: User
level: Intermediate
exl-id: 0d2417e9-5b3f-442d-a00d-8b4df239d952
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 2%

---

# Creazione dei rapporti sui percorsi {#concept_rfj_wpt_52b}


>[!CAUTION]
>
>**Cerchi Adobe Systems Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


## Accesso e creazione dei rapporti {#accessing-reports}

>[!NOTE]
>
>Dopo aver eliminato un percorso, tutti i rapporti associati non saranno più disponibili.

Questa sezione illustra come creare o utilizzare rapporti predefiniti. Combina pannelli, componenti e visualizzazioni per monitorare meglio il successo dei tuoi percorsi.

Per accedere ai rapporti dei tuoi percorsi e iniziare a monitorare il successo delle consegne:

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Home]**.

1. Seleziona il percorso su cui vuoi generare il rapporto.

   Puoi anche accedere ai tuoi report facendo clic su **Report** mentre passi il cursore del mouse su un percorso nell&#39;elenco dei percorsi.

   ![](../assets/dynamic_report_journey.png)

1. Fai clic sull&#39;icona **[!UICONTROL Report]** in alto a destra dello schermo.

   ![](../assets/dynamic_report_journey_2.png)

1. Il **[!UICONTROL Journey summary]** report predefinito viene visualizzato sullo schermo. Per accesso i rapporti personalizzati, fai clic sul **[!UICONTROL Close]** pulsante.

   ![](../assets/dynamic_report_journey_12.png)

1. Fai clic sul pulsante **[!UICONTROL Create new project]** per creare il rapporto da zero.

   ![](../assets/dynamic_report_journey_3.png)

1. **[!UICONTROL Panels]** Dal scheda, trascinare tutti i pannelli o le tabelle a forma libera necessari. Per ulteriori informazioni, consulta questa [sezione](#adding-panels).

   ![](../assets/dynamic_report_journey_4.png)

1. Puoi quindi iniziare a filtrare i dati trascinando dimensioni e metriche dalla scheda **[!UICONTROL Components]** alla tabella a forma libera. Per ulteriori informazioni, consulta questa [sezione](#adding-components).

   ![](../assets/dynamic_report_journey_5.png)

1. Per una visualizzazione più chiara dei dati, è possibile aggiungere visualizzazioni dalla scheda **[!UICONTROL Visualizations]**. Per ulteriori informazioni, consulta questa [sezione](#adding-visualizations).

## Aggiunta di pannelli{#adding-panels}

### Aggiunta di un pannello vuoto {#adding-a-blank-panel}

Per avviare il report, potete aggiungere una serie di pannelli a un report predefinito o personalizzato. Ogni pannello contiene diversi set di dati ed è composto da tabelle a forma libera e visualizzazioni.

Questo pannello consente di versione i rapporti in base alle esigenze. Puoi aggiungere nei rapporti tutti i pannelli desiderati per filtrare i dati in base a diversi periodi di tempo.

1. Fare clic sull&#39;icona **[!UICONTROL Panels]**. È inoltre possibile aggiungere un pannello facendo clic su **[!UICONTROL Insert tab]** e selezionando **[!UICONTROL New Blank Panel]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Trascina e rilascia **[!UICONTROL Blank Panel]** nel dashboard.

   ![](../assets/dynamic_report_panel.png)

Ora puoi aggiungere una tabella a forma libera al pannello per iniziare a eseguire il targeting dei dati.

### Aggiunta di una tabella a forma libera {#adding-a-freeform-table}

Le tabelle a forma libera consentono di creare una tabella per analizzare i dati utilizzando le diverse metriche e dimensioni disponibili nella tabella **[!UICONTROL Component]**.

Ogni tabella e visualizzazione è ridimensionabile e può essere spostata per personalizzare meglio il rapporto.

1. Fare clic sull&#39;icona **[!UICONTROL Panels]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Trascina e rilascia l&#39;elemento **[!UICONTROL Freeform]** nel dashboard.

   È inoltre possibile aggiungere una tabella facendo clic sulla scheda **[!UICONTROL Insert]** e selezionando **[!UICONTROL New Freeform]** oppure facendo clic su **[!UICONTROL Add a freeform table]** in un pannello vuoto.

   ![](../assets/dynamic_report_panel_2.png)

1. Trascinare gli elementi dalla scheda **[!UICONTROL Components]** nelle colonne e nelle righe per creare la tabella.

   ![](../assets/dynamic_report_freeform_3.png)

1. Fare clic sull&#39;icona per modificare la **[!UICONTROL Settings]** modalità di visualizzazione dei dati nelle colonne.

   ![](../assets/dynamic_report_freeform_4.png)

   **[!UICONTROL Column settings]** è composto da:

   * **[!UICONTROL Number]**: consente di mostrare o nascondere i numeri di riepilogo nella colonna.
   * **[!UICONTROL Percent]**: consente di mostrare o nascondere le percentuali nella colonna.
   * **[!UICONTROL Interpret zero as no value]**: consente di mostrare o nascondere quando il valore è uguale a zero.
   * **[!UICONTROL Background]**: consente di mostrare o nascondere la barra di avanzamento orizzontale nelle celle.
   * **[!UICONTROL Include retries]**: consente di includere i tentativi nel risultato. Questa funzione è disponibile solo per **[!UICONTROL Sent]** e **[!UICONTROL Bounces + Errors]**.

1. Selezionare una o più righe e fare clic sull&#39;icona **[!UICONTROL Visualize]** . Viene aggiunta una visualizzazione per riflettere le righe selezionate.

   ![](../assets/dynamic_report_freeform_5.png)

Ora puoi aggiungere tutti i componenti necessari e aggiungere visualizzazioni per fornire rappresentazioni grafiche dei dati.

## Aggiunta di componenti{#adding-components}

I componenti consentono di personalizzare i rapporti con dimensioni, metriche e periodi di tempo diversi.

1. Fare clic sulla scheda **[!UICONTROL Components]** per accedere all&#39;elenco dei componenti.

   ![](../assets/dynamic_report_components.png)

1. Ogni categoria visualizzata nella scheda **[!UICONTROL Components]** visualizza i cinque elementi più utilizzati. Fare clic sul nome di una categoria per accedere all&#39;elenco completo dei componenti.

   La tabella dei componenti è suddivisa in tre categorie:

   * **[!UICONTROL Dimensions]**: ottiene dettagli dal registro delle consegne, ad esempio il browser o il dominio del destinatario oppure il completamento di una consegna.
   * **[!UICONTROL Metrics]**: consente di ottenere dettagli sullo stato di un messaggio. Ad esempio, se un messaggio è stato recapitato e il utente lo ha aperto.
   * **[!UICONTROL Time]**: imposta un periodo di tempo per la tabella.

1. Trascina i componenti in un pannello per iniziare a filtrare i dati.

È possibile trascinare e rilasciare tutti i componenti necessari e confrontarli tra loro.

## Aggiunta di visualizzazioni{#adding-visualizations}

La scheda **[!UICONTROL Visualizations]** consente di trascinare e rilasciare gli elementi di visualizzazione, ad esempio area, anello e grafico. Le visualizzazioni forniscono rappresentazioni grafiche dei dati.

1. Nella scheda **[!UICONTROL Visualizations]**, trascina e rilascia un elemento di visualizzazione in un pannello.

   ![](../assets/dynamic_report_visualization_1.png)

1. Dopo aver aggiunto una visualizzazione al pannello, i rapporti rilevano automaticamente i dati nella tabella a forma libera. Seleziona le impostazioni per la visualizzazione.
1. Se sono presenti più tabelle a forma libera, scegliere l&#39;origine dati disponibile da aggiungere al grafico nella **[!UICONTROL Data Source Settings]** finestra. Questa finestra è disponibile anche facendo clic sul punto colorato accanto al titolo della visualizzazione.

   ![](../assets/dynamic_report_visualization_2.png)

1. Fare clic sul pulsante Impostazioni **[!UICONTROL Visualization]** per modificare direttamente il tipo di grafico o il contenuto visualizzato, ad esempio:

   * **[!UICONTROL Percentages]**: visualizza i valori in percentuale.
   * **[!UICONTROL Anchor Y Axis at Zero]**: forza l&#39;azzeramento dell&#39;asse y anche se i valori sono superiori a zero.
   * **[!UICONTROL Legend visible]**: consente di nascondere la legenda.
   * **[!UICONTROL Normalization]**: forza la corrispondenza dei valori.
   * **[!UICONTROL Display Dual Axis]**: aggiunge un altro asse al grafico.
   * **[!UICONTROL Limit Max Items]**: limita il numero di grafici visualizzati.
   * **[!UICONTROL Threshold]**: consente di impostare una soglia per il grafico. Viene visualizzata come una linea punteggiata nera.

   ![](../assets/dynamic_report_visualization_3.png)

Questa visualizzazione ti consente di avere una visione più chiara dei dati nei rapporti.
