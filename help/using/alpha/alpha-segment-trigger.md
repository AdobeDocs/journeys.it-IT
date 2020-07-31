---
title: Attività trigger segmento
description: Ulteriori informazioni su Trigger segmento
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
source-git-commit: b66cdb31b62b4627ff7378e48879ffadfedda5cb
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---


# Attività trigger segmento {#segment-trigger-activity}

## Informazioni sull&#39;attività Trigger segmento {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>Se un’attività di Adobe Campaign Standard fuori dalla casella è presente nell’area di lavoro  al momento della pubblicazione o dell’attivazione della modalità di prova, il viaggio sarà limitato a 13 ingressi al secondo. <br>Se &#39;attività out-of-the-box del Adobe Campaign Standard non è presente nell&#39;area di lavoro al momento della pubblicazione o al momento dell&#39;attivazione della modalità di prova, il viaggio sarà limitato a 1000 eventi al secondo.

L&#39;attività Trigger segmento consente di fare in modo che tutti gli individui appartenenti a un segmento di Adobe Experience Platform  entrino in un percorso. L&#39;ingresso in un viaggio può essere eseguito una volta o su base regolare.

Supponiamo che tu abbia un segmento di clienti Gold  Adobe Experience Platform. Con l&#39;attività Trigger segmento, puoi fare in modo che tutti gli individui appartenenti al segmento di clienti Gold entrino in un percorso e li facciano scorrere in percorsi personalizzati che sfrutteranno tutte le funzionalità di viaggio: condizioni, orari, eventi, azioni.

## Configurazione dell&#39;attività {#configuring-segment-trigger-activity}

>[!NOTE]
>
>A causa delle latenze di esportazione del segmento, non è possibile attivare un percorso basato su segmenti in un intervallo di tempo più breve di 1 ora.

1. Spiegate la **[!UICONTROL Orchestration]** categoria e rilasciate un&#39; **[!UICONTROL Segment Trigger]** attività nel quadro.

   L&#39;attività deve essere posizionata come primo passo di un viaggio.

1. Configurare l&#39;attività **[!UICONTROL Scheduler type]**.

   Per impostazione predefinita, il segmento entra nel percorso **[!UICONTROL As soon as possible]**, ovvero 1 ora dopo la pubblicazione del percorso. Se si desidera che il segmento entri nel percorso in una data/ora specifica o su base periodica, selezionare l&#39;opzione desiderata dall&#39;elenco.

   In caso di viaggi periodici, puoi anche definire l’inizio e la fine del viaggio.

   ![](../assets/segment-trigger-schedule.png)

1. Nel **[!UICONTROL Segment]** campo, scegliete il segmento di Adobe Experience Platform  che verrà inserito nel percorso, quindi fate clic su **[!UICONTROL Save]**.

   ![](../assets/segment-trigger-segment-selection.png)

1. Nel **[!UICONTROL Namespace]** campo, scegliete lo spazio dei nomi da utilizzare per identificare gli individui. For more on namespaces, refer to [this section](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Gli individui appartenenti a un segmento che non ha l&#39;identità selezionata (spazio dei nomi) tra le loro diverse identità non possono entrare nel percorso.

1. Fate clic **[!UICONTROL Ok]** per confermare. Puoi quindi sfruttare le attività disponibili per realizzare il tuo percorso.

1. Una volta che il viaggio è pronto, potete potenzialmente testarlo (vedete [Verifica del percorso](../building-journeys/testing-the-journey.md)).

   Quando la modalità di prova viene attivata in un viaggio che inizia con un’ **[!UICONTROL Segment Trigger]** attività, 100 profili di test verranno selezionati in modo casuale tra i profili idonei per il segmento selezionato. I registri di test consentiranno di visualizzare il percorso degli individui nel percorso e i potenziali errori riscontrati (consultate [Visualizzazione dei registri](../building-journeys/testing-the-journey.md#viewing_logs)).

   >[!NOTE]
   >
   >Notate che non potrete vedere le 100 persone che seguono il viaggio utilizzando la funzione di flusso visivo esistente nei viaggi unitari.

1. Potete quindi pubblicare il viaggio (consultate [Pubblicazione del percorso](../building-journeys/publishing-the-journey.md)). Gli individui appartenenti al segmento entreranno nel percorso nella data/ora specificata nel pianificatore attività Trigger segmento.

   >[!IMPORTANT]
   >
   >Tenere presente che  segmenti di Adobe Experience Platform vengono calcolati una volta al giorno (segmenti **batch** ) o in tempo reale (segmenti **in streaming** ).
   >
   >Se il segmento selezionato viene trasmesso in streaming, gli utenti appartenenti a questo segmento possono potenzialmente entrare nel viaggio in tempo reale. Se il segmento è batch, le persone appena qualificate per questo segmento entreranno potenzialmente nel percorso quando il calcolo del segmento viene eseguito sul Adobe Experience Platform .
