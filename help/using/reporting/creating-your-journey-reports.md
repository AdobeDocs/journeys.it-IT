---
product: adobe campaign
solution: Journey Orchestration
title: Creazione dei rapporti sui percorsi
description: Scopri come creare i rapporti sul viaggio
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 2%

---


# Creazione dei rapporti sui percorsi {#concept_rfj_wpt_52b}

## Accesso e creazione dei rapporti {#accessing-reports}

>[!NOTE]
>
>Dopo l’eliminazione di un viaggio, tutti i rapporti associati non saranno più disponibili.

In questa sezione viene illustrato come creare o utilizzare i rapporti out-of-the-box. Combinate pannelli, componenti e visualizzazioni per monitorare meglio il successo dei vostri viaggi.

Per accedere ai rapporti dei viaggi e iniziare a monitorare il successo delle consegne:

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Home]**.

1. Seleziona il percorso su cui vuoi effettuare il rapporto.

   È inoltre possibile accedere ai rapporti facendo clic su **Report** durante il passaggio del mouse su un viaggio nell&#39;elenco dei viaggi.

   ![](../assets/dynamic_report_journey.png)

1. Fate clic sull&#39;icona **[!UICONTROL Report]** in alto a destra dello schermo.

   ![](../assets/dynamic_report_journey_2.png)

1. Il rapporto **[!UICONTROL Journey summary]** out-of-the-box viene visualizzato sullo schermo. Per accedere ai rapporti personalizzati, fate clic sul pulsante **[!UICONTROL Close]**.

   ![](../assets/dynamic_report_journey_12.png)

1. Fai clic su **[!UICONTROL Create new project]** per creare un rapporto da zero.

   ![](../assets/dynamic_report_journey_3.png)

1. Dalla scheda **[!UICONTROL Panels]**, trascinare e rilasciare tutti i pannelli o le tabelle a forma libera necessari. Per ulteriori informazioni, consultare la sezione [sezione](#adding-panels).

   ![](../assets/dynamic_report_journey_4.png)

1. Puoi quindi iniziare a filtrare i dati trascinando dimensioni e metriche dalla scheda **[!UICONTROL Components]** alla tabella a forma libera. Per ulteriori informazioni, consultare la sezione [sezione](#adding-components).

   ![](../assets/dynamic_report_journey_5.png)

1. Per avere una visualizzazione più chiara dei dati, puoi aggiungere visualizzazioni dalla scheda **[!UICONTROL Visualizations]**. Per ulteriori informazioni, consultare la sezione [sezione](#adding-visualizations).

## Aggiunta di pannelli{#adding-panels}

### Aggiunta di un pannello vuoto {#adding-a-blank-panel}

Per avviare il rapporto, puoi aggiungere un set di pannelli a un rapporto out-of-the-box o personalizzato. Ciascun pannello contiene set di dati diversi ed è composto da tabelle e visualizzazioni a forma libera.

Questo pannello consente di creare i rapporti in base alle esigenze. Puoi aggiungere tutti i pannelli che desideri nei tuoi rapporti per filtrare i dati con periodi di tempo diversi.

1. Fate clic sull&#39;icona **[!UICONTROL Panels]**. Potete anche aggiungere un pannello facendo clic su **[!UICONTROL Insert tab]** e selezionando **[!UICONTROL New Blank Panel]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Trascinate e rilasciate **[!UICONTROL Blank Panel]** nel dashboard.

   ![](../assets/dynamic_report_panel.png)

Ora potete aggiungere una tabella a forma libera al pannello per avviare il targeting dei dati.

### Aggiunta di una tabella a forma libera {#adding-a-freeform-table}

Le tabelle a forma libera consentono di creare una tabella per analizzare i dati utilizzando le diverse metriche e dimensioni disponibili nella tabella **[!UICONTROL Component]**.

Ogni tabella e visualizzazione è ridimensionabile e può essere spostata per personalizzare meglio il rapporto.

1. Fate clic sull&#39;icona **[!UICONTROL Panels]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Trascinate e rilasciate l&#39;elemento **[!UICONTROL Freeform]** nel dashboard.

   È inoltre possibile aggiungere una tabella facendo clic sulla scheda **[!UICONTROL Insert]** e selezionando **[!UICONTROL New Freeform]** oppure facendo clic su **[!UICONTROL Add a freeform table]** in un pannello vuoto.

   ![](../assets/dynamic_report_panel_2.png)

1. Trascinare gli elementi dalla scheda **[!UICONTROL Components]** nelle colonne e nelle righe per creare la tabella.

   ![](../assets/dynamic_report_freeform_3.png)

1. Fare clic sull&#39;icona **[!UICONTROL Settings]** per modificare la modalità di visualizzazione dei dati nelle colonne.

   ![](../assets/dynamic_report_freeform_4.png)

   La **[!UICONTROL Column settings]** è composta da:

   * **[!UICONTROL Number]**: consente di mostrare o nascondere i numeri di riepilogo nella colonna.
   * **[!UICONTROL Percent]**: consente di mostrare o nascondere le percentuali nella colonna.
   * **[!UICONTROL Interpret zero as no value]**: consente di visualizzare o nascondere quando un valore è uguale a zero.
   * **[!UICONTROL Background]**: consente di mostrare o nascondere la barra di avanzamento orizzontale nelle celle.
   * **[!UICONTROL Include retries]**: consente di includere i tentativi nel risultato. Questa funzione è disponibile solo per **[!UICONTROL Sent]** e **[!UICONTROL Bounces + Errors]**.

1. Selezionare una o più righe e fare clic sull&#39;icona **[!UICONTROL Visualize]**. Viene aggiunta una visualizzazione per riflettere le righe selezionate.

   ![](../assets/dynamic_report_freeform_5.png)

Ora puoi aggiungere tutti i componenti necessari e anche aggiungere visualizzazioni per fornire rappresentazioni grafiche dei tuoi dati.

## Aggiunta di componenti{#adding-components}

I componenti consentono di personalizzare i rapporti con dimensioni, metriche e periodi di tempo diversi.

1. Fare clic sulla scheda **[!UICONTROL Components]** per accedere all&#39;elenco dei componenti.

   ![](../assets/dynamic_report_components.png)

1. Ogni categoria presentata nella scheda **[!UICONTROL Components]** visualizza i cinque elementi più utilizzati, fate clic sul nome di una categoria per accedere al relativo elenco completo di componenti.

   La tabella dei componenti è suddivisa in tre categorie:

   * **[!UICONTROL Dimensions]**: Ottenete i dettagli dal registro delle consegne, ad esempio il browser o il dominio del destinatario, o l&#39;esito positivo di una consegna.
   * **[!UICONTROL Metrics]**: Ottieni informazioni sullo stato di un messaggio. Ad esempio, se un messaggio è stato recapitato e l&#39;utente lo ha aperto.
   * **[!UICONTROL Time]**: Impostare un periodo di tempo per la tabella.

1. Trascinate e rilasciate i componenti in un pannello per iniziare a filtrare i dati.

Puoi trascinare e rilasciare tutti i componenti necessari e confrontarli tra loro.

## Aggiunta di visualizzazioni{#adding-visualizations}

La scheda **[!UICONTROL Visualizations]** consente di trascinare e rilasciare elementi di visualizzazione, ad esempio area, ciambella e grafico. Le visualizzazioni forniscono rappresentazioni grafiche dei dati.

1. Nella scheda **[!UICONTROL Visualizations]**, trascina e rilascia un elemento di visualizzazione in un pannello.

   ![](../assets/dynamic_report_visualization_1.png)

1. Dopo aver aggiunto una visualizzazione al pannello, i report rileveranno automaticamente i dati nella tabella a forma libera. Seleziona le impostazioni per la visualizzazione.
1. Se si dispone di più tabelle a forma libera, scegliere l&#39;origine dati disponibile da aggiungere nel grafico nella finestra **[!UICONTROL Data Source Settings]**. Questa finestra è disponibile anche facendo clic sul punto colorato accanto al titolo della visualizzazione.

   ![](../assets/dynamic_report_visualization_2.png)

1. Fate clic sul pulsante **[!UICONTROL Visualization]** delle impostazioni per modificare direttamente il tipo di grafico o il contenuto visualizzato, ad esempio:

   * **[!UICONTROL Percentages]**: Visualizza i valori in percentuale.
   * **[!UICONTROL Anchor Y Axis at Zero]**: Forza l&#39;asse y a zero anche se i valori sono superiori a zero.
   * **[!UICONTROL Legend visible]**: Ti permette di nascondere la leggenda.
   * **[!UICONTROL Normalization]**: Forza la corrispondenza dei valori.
   * **[!UICONTROL Display Dual Axis]**: Aggiunge un altro asse al grafico.
   * **[!UICONTROL Limit Max Items]**: Limita il numero di grafici visualizzati.
   * **[!UICONTROL Threshold]**: Consente di impostare una soglia per il grafico. Viene visualizzata come una linea punteggiata nera.

   ![](../assets/dynamic_report_visualization_3.png)

Questa visualizzazione consente di avere una visualizzazione più chiara dei dati nei rapporti.