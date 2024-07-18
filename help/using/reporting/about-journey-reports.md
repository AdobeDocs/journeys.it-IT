---
product: adobe campaign
title: Informazioni sui rapporti sui percorsi
description: Scopri come creare i rapporti di percorso
feature: Journeys
role: User
level: Intermediate
exl-id: 93768321-b171-4338-a440-6ea189a85a4a
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---

# Informazioni sui rapporti sui percorsi {#concept_rfj_wpt_52b}

>[!NOTE]
>
>I dati di consegna e il componente Segmenti verranno compilati solo se si dispone di Adobe Campaign Standard.

Questa sezione illustra come accedere ai rapporti e utilizzarli per misurare l’efficacia dei tuoi percorsi.

## Interfaccia di generazione rapporti {#reporting-interface}

La barra degli strumenti superiore consente, ad esempio, di modificare, salvare o stampare il report.

![](../assets/dynamic_report_toolbar.png)

Utilizzare la scheda **[!UICONTROL Project]** per:

* **[!UICONTROL Open]**: apre un report o un modello creato in precedenza.
* **[!UICONTROL Save As]**: duplica i modelli per poterli modificare.
* **[!UICONTROL Refresh project]**: aggiorna il report in base ai nuovi dati e alle modifiche apportate ai filtri.
* **[!UICONTROL Download CSV]**: esporta i rapporti in un file CSV.
* **[!UICONTROL Print]**: stampa il report.

La scheda **[!UICONTROL Edit]** consente di:

* **[!UICONTROL Undo]**: annulla l&#39;ultima azione nel dashboard.
* **[!UICONTROL Redo]**: annulla l&#39;ultima azione **[!UICONTROL Undo]** nel dashboard.
* **[!UICONTROL Clear all]**: elimina tutti i pannelli del dashboard.

La tabella **[!UICONTROL Insert]** consente di personalizzare i report aggiungendo grafici e tabelle al dashboard:

* **[!UICONTROL New Blank Panel]**: aggiunge un nuovo pannello vuoto alla dashboard.
* **[!UICONTROL New Freeform]**: aggiunge una nuova tabella a forma libera alla dashboard.
* **[!UICONTROL New Line]**: aggiunge un nuovo grafico a linee al dashboard.
* **[!UICONTROL New Bar]**: aggiunge un nuovo grafico a barre al dashboard.

Le schede a sinistra ti consentono di creare il rapporto e filtrare i dati in base alle esigenze.

![](../assets/dynamic_report_interface.png)

Queste schede consentono di accedere ai seguenti elementi:

* **[!UICONTROL Panels]**: aggiungi un pannello vuoto o una figura a mano libera al report per iniziare a filtrare i dati. Per ulteriori informazioni, consulta la sezione [Aggiunta di pannelli](../reporting/creating-your-journey-reports.md#adding-panels)
* **[!UICONTROL Visualizations]**: trascina una selezione di elementi di visualizzazione per conferire al rapporto una dimensione grafica. Per ulteriori informazioni, consulta la sezione [Aggiunta di visualizzazioni](../reporting/creating-your-journey-reports.md#adding-visualizations).
* **[!UICONTROL Components]**: personalizza i tuoi rapporti con dimensioni, metriche, segmenti e periodi di tempo diversi. Per ulteriori informazioni, consulta la sezione [Aggiunta di componenti](../reporting/creating-your-journey-reports.md#adding-components).

## Modello di riepilogo percorso {#ootb-template}

I rapporti sono suddivisi in due categorie: un modello preconfigurato e rapporti personalizzati.
Il modello predefinito **[!UICONTROL Journey summary]** offre una visualizzazione chiara dei dati di tracciamento più importanti.

![](../assets/dynamic_report_journey_8.png)

Ogni tabella è rappresentata da numeri e grafici di riepilogo. Puoi modificare la modalità di visualizzazione dei dettagli nelle rispettive impostazioni di visualizzazione.

Nella parte superiore del rapporto sono disponibili i KPI seguenti:

* **[!UICONTROL Journey - Entered]**: numero totale di singoli utenti che hanno raggiunto l&#39;evento di ingresso del percorso.
* **[!UICONTROL Journey - Completion rate]**: numero totale di individui che hanno raggiunto la fine del percorso (o nel caso di un individuo che non soddisfa alcuna condizione) rispetto al numero totale di individui che sono entrati nel percorso.
* **[!UICONTROL Journey - Current]**: numero totale di individui attualmente nel percorso.
* **[!UICONTROL Journey - Failed rate]**: numero totale di percorsi non eseguiti correttamente rispetto al numero di percorsi eseguiti.
* **[!UICONTROL Delivery - Messages sent]**: numero totale di messaggi inviati.
* **[!UICONTROL Delivery rate]**: numero totale di messaggi consegnati correttamente rispetto ai messaggi inviati.
* **[!UICONTROL Delivery - Bounce rate]**: numero totale di messaggi non recapitati rispetto ai messaggi inviati.
* **[!UICONTROL Delivery - Unsubscribed rate]**: numero totale di annullamenti di abbonamenti per destinatario rispetto ai messaggi consegnati.
* **[!UICONTROL Delivery - Open rate]**: numero totale di messaggi aperti rispetto al numero di messaggi recapitati.
* **[!UICONTROL Delivery - Click rate]**: numero totale di clic in una consegna rispetto al numero di messaggi consegnati.

La visualizzazione del flusso di Percorso ti consente di visualizzare passo dopo passo il percorso dei profili target nel percorso. Questa opzione è disponibile solo quando si esegue il targeting di un percorso. Viene generato automaticamente e non può essere modificato.

![](../assets/dynamic_report_journey_10.png)

La tabella **[!UICONTROL Journey summary]** contiene i dati disponibili per il percorso, ad esempio:

* **[!UICONTROL Entered]**: numero totale di singoli utenti che hanno raggiunto l&#39;evento di ingresso del percorso.
* **[!UICONTROL Completion rate]**: numero totale di individui che hanno raggiunto il controllo del flusso finale del percorso rispetto al numero totale di individui che sono entrati nel percorso.
* **[!UICONTROL Current]**: numero totale di individui attualmente nel percorso.
* **[!UICONTROL Failed]**: numero totale di percorsi non eseguiti correttamente.
* **[!UICONTROL Failed rate]**: numero totale di percorsi non eseguiti correttamente rispetto al numero di percorsi eseguiti.

Nella tabella **[!UICONTROL Top events]** sono visualizzati gli eventi di maggior successo e **[!UICONTROL Top action]**, le azioni di maggior successo nei tuoi percorsi.

![](../assets/dynamic_report_journey_11.png)

La tabella **[!UICONTROL Delivery - Sending summary]** contiene i dati disponibili per le consegne del percorso, ad esempio:

* **[!UICONTROL Processed/sent]**: numero totale di messaggi inviati.
* **[!UICONTROL Delivered rate]**: numero totale di messaggi consegnati correttamente rispetto ai messaggi inviati.
* **[!UICONTROL Delivered]**: numero di messaggi inviati correttamente, in relazione al numero totale di messaggi inviati.
* **[!UICONTROL Bounce + error rate]**: numero totale di messaggi non recapitati rispetto ai messaggi inviati.
* **[!UICONTROL Bounces + errors]**: totale degli errori cumulati durante la consegna e l&#39;elaborazione automatica della restituzione in relazione al numero totale di messaggi inviati.

La tabella **[!UICONTROL Delivery - Tracking summary]** contiene i dati disponibili per tenere traccia del completamento delle consegne dei tuoi percorsi, ad esempio:

* **[!UICONTROL Open Rate]**: percentuale di messaggi aperti.
* **[!UICONTROL Open]**: numero di volte in cui un messaggio è stato aperto in una consegna.
* **[!UICONTROL Click trough rate]**: numero totale di clic in una consegna rispetto al numero di messaggi consegnati.
* **[!UICONTROL Click]**: numero di volte in cui è stato fatto clic su un contenuto in una consegna.
* **[!UICONTROL Unsubscribe rate]**: percentuale di annullamenti di abbonamenti per destinatario rispetto ai messaggi consegnati.
* **[!UICONTROL Unsubscribed]**: numero totale di annullamenti di abbonamenti per destinatario rispetto ai messaggi consegnati.
