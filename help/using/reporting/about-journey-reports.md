---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sui rapporti sui percorsi
description: Scopri come creare i rapporti sul viaggio
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---


# Informazioni sui rapporti sui percorsi {#concept_rfj_wpt_52b}

>[!NOTE]
>
>I dati di distribuzione e il componente Segmenti verranno compilati solo se si dispone  Adobe Campaign Standard.

In questa sezione viene illustrato come accedere e utilizzare i rapporti per misurare l&#39;efficacia dei viaggi.

## Interfaccia di reporting {#reporting-interface}

La barra degli strumenti superiore consente, ad esempio, di modificare, salvare o stampare il rapporto.

![](../assets/dynamic_report_toolbar.png)

Utilizzate la scheda **[!UICONTROL Project]** per:

* **[!UICONTROL Open]**: apre un report o un modello creato in precedenza.
* **[!UICONTROL Save As]**: duplica i modelli per modificarli.
* **[!UICONTROL Refresh project]**: aggiorna il rapporto in base ai nuovi dati e alle modifiche apportate ai filtri.
* **[!UICONTROL Download CSV]**: esporta i rapporti in un file CSV.
* **[!UICONTROL Print]**: stampa il rapporto.

La scheda **[!UICONTROL Edit]** consente di:

* **[!UICONTROL Undo]**: annulla l’ultima azione sul dashboard.
* **[!UICONTROL Redo]**: annulla l’ultima  **[!UICONTROL Undo]** azione sul dashboard.
* **[!UICONTROL Clear all]**: elimina tutti i pannelli del dashboard.

La tabella **[!UICONTROL Insert]** consente di personalizzare i rapporti aggiungendo grafici e tabelle al dashboard:

* **[!UICONTROL New Blank Panel]**: aggiunge un nuovo pannello vuoto al dashboard.
* **[!UICONTROL New Freeform]**: aggiunge una nuova tabella a forma libera al dashboard.
* **[!UICONTROL New Line]**: aggiunge un nuovo grafico a linee al dashboard.
* **[!UICONTROL New Bar]**: aggiunge un nuovo grafico a barre al dashboard.

Le schede a sinistra consentono di creare il rapporto e di filtrare i dati in base alle esigenze.

![](../assets/dynamic_report_interface.png)

Queste schede consentono di accedere ai seguenti elementi:

* **[!UICONTROL Panels]**: aggiungi un pannello vuoto o una forma libera al rapporto per iniziare a filtrare i dati. Per ulteriori informazioni, consultare la sezione [Aggiunta di pannelli](../reporting/creating-your-journey-reports.md#adding-panels)
* **[!UICONTROL Visualizations]**: trascina e rilascia una selezione di elementi di visualizzazione per conferire al rapporto una dimensione grafica. Per ulteriori informazioni, consultare la sezione [Aggiunta di visualizzazioni](../reporting/creating-your-journey-reports.md#adding-visualizations).
* **[!UICONTROL Components]**: personalizzare i rapporti con dimensioni, metriche, segmenti e periodi di tempo diversi. Per ulteriori informazioni, consultare la sezione [Aggiunta di componenti](../reporting/creating-your-journey-reports.md#adding-components).

## Modello riepilogo percorso {#ootb-template}

I rapporti sono suddivisi in due categorie: un modello integrato e rapporti personalizzati.
Il modello out-of-the-box, **[!UICONTROL Journey summary]**, offre una visualizzazione chiara dei dati di tracciamento più importanti.

![](../assets/dynamic_report_journey_8.png)

Ogni tabella è rappresentata da numeri e grafici di riepilogo. Puoi modificare la modalità di visualizzazione dei dettagli nelle rispettive impostazioni di visualizzazione.

I seguenti KPI sono disponibili nella parte superiore del report:

* **[!UICONTROL Journey - Entered]**: numero totale di persone che hanno raggiunto l&#39;evento di ingresso del viaggio.
* **[!UICONTROL Journey - Completion rate]**: numero totale di persone che hanno raggiunto la fine del viaggio (o nel caso di una persona che non soddisfa nessuna condizione) rispetto al numero totale di persone che sono entrate nel viaggio.
* **[!UICONTROL Journey - Current]**: numero totale di persone attualmente in viaggio.
* **[!UICONTROL Journey - Failed rate]**: numero totale di viaggi che non sono stati eseguiti con successo rispetto al numero di percorsi di esecuzione.
* **[!UICONTROL Delivery - Messages sent]**: numero totale di messaggi inviati.
* **[!UICONTROL Delivery rate]**: numero totale di messaggi consegnati correttamente rispetto ai messaggi inviati.
* **[!UICONTROL Delivery - Bounce rate]**: numero totale di messaggi rimbalzati rispetto ai messaggi inviati.
* **[!UICONTROL Delivery - Unsubscribed rate]**: numero totale di sottoscrizioni per destinatario rispetto ai messaggi consegnati.
* **[!UICONTROL Delivery - Open rate]**: numero totale di messaggi aperti rispetto al numero di messaggi inviati.
* **[!UICONTROL Delivery - Click rate]**: numero totale di clic in una consegna rispetto al numero di messaggi inviati.

La visualizzazione del flusso di lavoro del viaggio consente di visualizzare il percorso dei profili di destinazione passo passo nel percorso. Questa funzione è disponibile solo quando si esegue il targeting di un percorso. Viene generato automaticamente e non può essere modificato.

![](../assets/dynamic_report_journey_10.png)

La tabella **[!UICONTROL Journey summary]** contiene i dati disponibili per il viaggio, ad esempio:

* **[!UICONTROL Entered]**: numero totale di persone che hanno raggiunto l&#39;evento di ingresso del viaggio.
* **[!UICONTROL Completion rate]**: numero totale di persone che hanno raggiunto il controllo del flusso finale del viaggio rispetto al numero totale di persone che sono entrate nel viaggio.
* **[!UICONTROL Current]**: numero totale di persone attualmente in viaggio.
* **[!UICONTROL Failed]**: numero totale di viaggi che non sono stati eseguiti correttamente.
* **[!UICONTROL Failed rate]**: numero totale di viaggi che non sono stati eseguiti con successo rispetto al numero di percorsi di esecuzione.

La tabella **[!UICONTROL Top events]** mostra gli eventi di maggior successo e le **[!UICONTROL Top action]** azioni di maggior successo nei vostri viaggi.

![](../assets/dynamic_report_journey_11.png)

La tabella **[!UICONTROL Delivery - Sending summary]** contiene i dati disponibili per le consegne del viaggio, ad esempio:

* **[!UICONTROL Processed/sent]**: numero totale di messaggi inviati.
* **[!UICONTROL Delivered rate]**: numero totale di messaggi consegnati correttamente rispetto ai messaggi inviati.
* **[!UICONTROL Delivered]**: numero di messaggi inviati con successo, in relazione al numero totale di messaggi inviati.
* **[!UICONTROL Bounce + error rate]**: numero totale di messaggi rimbalzati rispetto ai messaggi inviati.
* **[!UICONTROL Bounces + errors]**: totale degli errori cumulati durante l&#39;elaborazione della consegna e della restituzione automatica in relazione al numero totale di messaggi inviati.

La tabella **[!UICONTROL Delivery - Tracking summary]** contiene i dati disponibili per monitorare il successo delle consegne dei viaggi, ad esempio:

* **[!UICONTROL Open Rate]**: percentuale di messaggi aperti.
* **[!UICONTROL Open]**: il numero di volte in cui un messaggio è stato aperto in una consegna.
* **[!UICONTROL Click trough rate]**: numero totale di clic in una consegna rispetto al numero di messaggi inviati.
* **[!UICONTROL Click]**: numero di volte in cui è stato fatto clic su un contenuto in una consegna.
* **[!UICONTROL Unsubscribe rate]**: percentuale di annullamento sottoscrizioni per destinatario rispetto ai messaggi consegnati.
* **[!UICONTROL Unsubscribed]**: numero totale di sottoscrizioni per destinatario rispetto ai messaggi consegnati.
