---
product: adobe campaign
solution: Journey Orchestration
title: Eventi di qualificazione dei segmenti
description: Scopri gli eventi di qualificazione dei segmenti
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 1%

---


# Eventi di qualificazione dei segmenti {#segment-qualification}

## Informazioni sugli eventi di qualificazione dei segmenti{#about-segment-qualification}

Questa attività consente al tuo percorso di ascoltare le entrate e le uscite dei profili nei segmenti Adobe Experience Platform per consentire ai singoli utenti di entrare o proseguire in un percorso. Per ulteriori informazioni sulla creazione dei segmenti, consulta questa [sezione](../segment/about-segments.md).

Supponiamo che tu abbia un segmento &quot;cliente argento&quot;. Con questa attività, puoi fare entrare tutti i nuovi clienti in argento in un percorso e inviare loro una serie di messaggi personalizzati.

Questo tipo di evento può essere posizionato come primo passaggio o successivo nel percorso.

>[!IMPORTANT]
>
>Tieni presente che i segmenti Adobe Experience Platform vengono calcolati una volta al giorno (**batch** segmenti) o in tempo reale (**in streaming** segmenti, utilizzando l’opzione Tipi di pubblico ad alta frequenza di Adobe Experience Platform).
>
>Se il segmento selezionato viene trasmesso in streaming, i singoli utenti appartenenti a questo segmento potrebbero accedere al percorso in tempo reale. Se il segmento è batch, le persone appena qualificate per questo segmento potranno potenzialmente entrare nel percorso quando il calcolo del segmento viene eseguito su Adobe Experience Platform.


1. Apri la categoria **[!UICONTROL Events]** e rilascia un’attività **[!UICONTROL Segment qualification]** nell’area di lavoro.

   ![](../assets/segment5.png)

1. Aggiungi un **[!UICONTROL Label]** all’attività. Questo passaggio è facoltativo.

1. Fai clic sul campo **[!UICONTROL Segment]** e seleziona i segmenti che desideri sfruttare.

   >[!NOTE]
   >
   >È possibile personalizzare e ordinare le colonne visualizzate nell’elenco.

   ![](../assets/segment6.png)

   Una volta aggiunto il segmento, il pulsante **[!UICONTROL Copy]** ti consente di copiarne il nome e l’ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. Nel campo **[!UICONTROL Behaviour]** , scegli se desideri ascoltare le entrate, le uscite o entrambi dei segmenti.

   >[!NOTE]
   >
   >Tieni presente che **[!UICONTROL Enter]** e **[!UICONTROL Exit]** corrispondono agli stati di partecipazione al segmento **Realized** e **Exited** da Adobe Experience Platform. Per ulteriori informazioni su come valutare un segmento, consulta la [documentazione del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

1. Seleziona uno spazio dei nomi. Questa opzione è necessaria solo se l’evento è posizionato come primo passaggio del percorso.

   ![](../assets/segment7.png)

Il payload contiene le seguenti informazioni contestuali, utilizzabili in condizioni e azioni:

* il comportamento (entrata, uscita)
* la marca temporale della qualifica
* id del segmento

Quando utilizzi l’editor espressioni in una condizione o azione che segue un’attività **[!UICONTROL Segment qualification]**, puoi accedere al nodo **[!UICONTROL SegmentQualification]** . Puoi scegliere tra **[!UICONTROL Last qualification time]** e **[!UICONTROL status]** (enter o exit).

Consulta [Attività condizione](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

## Best practice {#best-practices-segments}

L’ attività **[!UICONTROL Segment Qualification]** consente l’ingresso immediato in percorsi di persone qualificate o squalificate da un segmento Adobe Experience Platform.

La velocità di ricezione di queste informazioni è elevata. Le misurazioni effettuate mostrano una velocità di 10 000 eventi ricevuti al secondo. Di conseguenza, è necessario assicurarsi di comprendere come possono accadere picchi di ingresso, come evitarli e come rendere il percorso pronto per loro.

### Segmenti batch{#batch-speed-segment-qualification}

Quando si utilizza la qualificazione dei segmenti per un segmento batch, si noti che al momento del calcolo giornaliero si verifica un picco di entrata. La dimensione del picco dipenderà dal numero di persone che entrano (o escono) quotidianamente nel segmento.

Inoltre, se il segmento batch viene creato di recente e utilizzato immediatamente in un percorso, il primo batch di calcoli potrebbe fare entrare un numero molto elevato di persone nel percorso.

### Segmenti in streaming{#streamed-speed-segment-qualification}

Quando si utilizza la qualifica del segmento per i segmenti in streaming, si corre il rischio di ottenere picchi di entrate/uscite di grandi dimensioni a causa della valutazione continua del segmento. Tuttavia, se la definizione del segmento porta a rendere un grande volume di clienti qualificati allo stesso tempo, potrebbe esserci anche un picco.

Per ulteriori informazioni sulla segmentazione in streaming, consulta questa [pagina](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### Come evitare gli overload{#overloads-speed-segment-qualification}

Di seguito sono riportate alcune best practice che aiuteranno a evitare il sovraccarico dei sistemi sfruttati nei percorsi (origini dati, azioni personalizzate, azioni Adobe Campaign Standard).

Non utilizzare, in un&#39;attività **[!UICONTROL Segment Qualification]**, un segmento batch immediatamente dopo la creazione. Evita il primo picco di calcolo. Se stai per utilizzare un segmento che non è mai stato calcolato, nell’area di lavoro del percorso verrà visualizzato un avviso giallo.

![](../assets/segment-error.png)

Inserisci una regola di limitazione per le origini dati e le azioni utilizzate nei percorsi per evitare di sovraccaricarle (consulta questa [sezione](../api/capping.md)). La regola di tappatura non ha alcun nuovo tentativo. Per riprovare, è necessario utilizzare un percorso alternativo nel percorso selezionando la casella **[!UICONTROL Add an alternative path in case of a timeout or an error]** in condizioni o azioni.

Prima di utilizzare il segmento in un percorso di produzione, valuta sempre prima il volume di individui che si qualificano per questo segmento ogni giorno. Per farlo, puoi controllare la sezione **[!UICONTROL Segments]** in Adobe Experience Platform e guardare il grafico sul lato destro.

![](../assets/segment-overload.png)
