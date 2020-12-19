---
product: adobe campaign
solution: Journey Orchestration
title: Eventi di qualificazione dei segmenti
description: Scopri gli eventi di qualifica dei segmenti
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 1%

---


# Eventi di qualificazione dei segmenti {#segment-qualification}

## Informazioni sugli eventi di qualificazione dei segmenti{#about-segment-qualification}

Questa attività consente al tuo viaggio di ascoltare le entrate e le uscite dei profili nei segmenti Adobe Experience Platform per far entrare o far avanzare gli individui in un viaggio. Per ulteriori informazioni sulla creazione dei segmenti, consultare la sezione [sezione](../segment/about-segments.md).

Supponiamo che tu abbia un segmento &quot;cliente argento&quot;. Con questa attività, puoi far entrare tutti i nuovi clienti in argento in un viaggio e inviare loro una serie di messaggi personalizzati.

Questo tipo di evento può essere posizionato come primo passo o successivo del viaggio.

>[!IMPORTANT]
>
>Tenere presente che i segmenti Adobe Experience Platform vengono calcolati una volta al giorno (**batch** segmenti) o in tempo reale (**in streaming** segmenti, utilizzando l&#39;opzione Pubblico ad alta frequenza di Adobe Experience Platform).
>
>Se il segmento selezionato viene trasmesso in streaming, gli utenti appartenenti a questo segmento possono potenzialmente entrare nel percorso in tempo reale. Se il segmento è batch, le persone appena qualificate per questo segmento potranno potenzialmente entrare nel percorso quando il calcolo del segmento viene eseguito sull&#39;Adobe Experience Platform.


1. Spiegate la categoria **[!UICONTROL Events]** e rilasciate un&#39;attività **[!UICONTROL Segment qualification]** nel quadro.

   ![](../assets/segment5.png)

1. Aggiungete un elemento **[!UICONTROL Label]** all&#39;attività. Questo passaggio è facoltativo.

1. Fare clic nel campo **[!UICONTROL Segment]** e selezionare i segmenti che si desidera sfruttare.

   >[!NOTE]
   >
   >È possibile personalizzare le colonne visualizzate nell&#39;elenco e ordinarle.

   ![](../assets/segment6.png)

   Una volta aggiunto il segmento, il pulsante **[!UICONTROL Copy]** consente di copiarne il nome e l&#39;ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. Nel campo **[!UICONTROL Behavior]**, scegliere se si desidera ascoltare le entrate, le uscite o entrambi del segmento.

1. Selezionare uno spazio nomi. Questo è necessario solo se l&#39;evento è posizionato come primo passo del viaggio.

   ![](../assets/segment7.png)

Il payload contiene le seguenti informazioni contestuali, che potete utilizzare in condizioni e azioni:

* il comportamento (entrata, uscita)
* la marca temporale della qualifica
* l’ID del segmento

Quando si utilizza l&#39;editor di espressioni in una condizione o azione che segue un&#39;attività **[!UICONTROL Segment qualification]**, è possibile accedere al nodo **[!UICONTROL SegmentQualification]**. È possibile scegliere tra **[!UICONTROL Last qualification time]** e **[!UICONTROL status]** (immettere o uscire).

Vedere [Attività delle condizioni](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

## Best practice {#best-practices-segments}

L&#39;attività **[!UICONTROL Segment Qualification]** consente l&#39;ingresso immediato nei viaggi di persone qualificate o squalificate da un segmento Adobe Experience Platform.

La velocità di ricezione di queste informazioni è elevata. Le misurazioni effettuate mostrano una velocità di 10 000 eventi ricevuti al secondo. Di conseguenza, devi accertarti di capire come possono accadere picchi di ingresso, come evitarli e come rendere il tuo viaggio pronto per loro.

### Segmenti batch{#batch-speed-segment-qualification}

Quando si utilizza la qualifica del segmento per un segmento batch, si noti che al momento del calcolo giornaliero si verificherà un picco di ingresso. La dimensione del picco dipende dal numero di persone che entrano (o escono) ogni giorno nel segmento.

Inoltre, se il segmento batch viene creato di recente e utilizzato immediatamente in un viaggio, il primo batch di calcoli potrebbe far entrare un numero molto elevato di persone nel viaggio.

### Segmenti in streaming{#streamed-speed-segment-qualification}

Quando si utilizza la qualifica del segmento per i segmenti in streaming, il rischio di ottenere picchi di entrate/uscite elevati è minore a causa della valutazione continua del segmento. Tuttavia, se la definizione del segmento porta a rendere un volume elevato di clienti idonei allo stesso tempo, potrebbe verificarsi anche un picco.

Per ulteriori informazioni sulla segmentazione in streaming, fare riferimento a questa [pagina](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### Come evitare i sovraccarichi{#overloads-speed-segment-qualification}

Di seguito sono riportate alcune best practice che aiuteranno a evitare il sovraccarico dei sistemi utilizzati nei viaggi (origini dati, azioni personalizzate,  azioni Adobe Campaign Standard).

Non utilizzare, in un&#39;attività **[!UICONTROL Segment Qualification]**, un segmento batch subito dopo la creazione. Si eviterà il primo picco di calcolo. Si noti che nell&#39;area di viaggio sarà visualizzato un avviso giallo se state per utilizzare un segmento che non è mai stato calcolato.

![](../assets/segment-error.png)

Inserire una regola di limite per le origini dati e le azioni utilizzate nei viaggi per evitare il sovraccarico (fare riferimento a questa [sezione](../api/capping.md)). Tenere presente che la regola di capping non dispone di nuovi tentativi. Per riprovare, è necessario utilizzare un percorso alternativo nel percorso selezionando la casella **[!UICONTROL Add an alternative path in case of a timeout or an error]** in condizioni o azioni.

Prima di utilizzare il segmento in un percorso di produzione, valuta sempre prima il volume di individui che soddisfano questo segmento ogni giorno. A tal fine, potete controllare la sezione **[!UICONTROL Segments]** nell&#39;Adobe Experience Platform e guardare il grafico sul lato destro.

![](../assets/segment-overload.png)
