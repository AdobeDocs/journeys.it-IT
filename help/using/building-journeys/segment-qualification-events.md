---
product: adobe campaign
title: Eventi di qualificazione dei segmenti
description: Scopri gli eventi di qualificazione dei segmenti
feature: Journeys
role: User
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 1%

---

# Eventi di qualificazione dei segmenti {#segment-qualification}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._



## Informazioni sugli eventi di qualificazione dei segmenti{#about-segment-qualification}

Questa attività consente al percorso di ascoltare le entrate e le uscite dei profili nei segmenti Adobe Experience Platform per consentire a singoli utenti di entrare o proseguire in un percorso. Per ulteriori informazioni sulla creazione dei segmenti, consulta questa [sezione](../segment/about-segments.md).

Supponiamo che tu abbia un segmento &quot;cliente silver&quot;. Con questa attività, puoi fare in modo che tutti i nuovi clienti silver entrino in un percorso e inviino loro una serie di messaggi personalizzati.

Questo tipo di evento può essere posizionato come primo passaggio o successivamente nel percorso.

>[!IMPORTANT]
>
>Tieni presente che i segmenti di Adobe Experience Platform vengono calcolati una volta al giorno (**batch** segmenti) o in tempo reale (**flussi** segmenti, utilizzando l&#39;opzione Tipi di pubblico ad alta frequenza di Adobe Experience Platform).
>
>Se il segmento selezionato viene inviato in streaming, i singoli utenti appartenenti a questo segmento potrebbero entrare nel percorso in tempo reale. Se il segmento è batch, le persone appena qualificate per questo segmento potrebbero entrare nel percorso quando il calcolo del segmento viene eseguito su Adobe Experience Platform.


1. Espandi la categoria **[!UICONTROL Events]** e rilascia un&#39;attività **[!UICONTROL Segment qualification]** nell&#39;area di lavoro.

   ![](../assets/segment5.png)

1. Aggiungi **[!UICONTROL Label]** all&#39;attività. Questo passaggio è facoltativo.

1. Fai clic nel campo **[!UICONTROL Segment]** e seleziona i segmenti che desideri sfruttare.

   >[!NOTE]
   >
   >Si noti che è possibile personalizzare le colonne visualizzate nell&#39;elenco e ordinarle.

   ![](../assets/segment6.png)

   Una volta aggiunto il segmento, il pulsante **[!UICONTROL Copy]** ti consente di copiarne il nome e l&#39;ID:

   `{"name":"Loyalty membership","id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. Nel campo **[!UICONTROL Behaviour]**, scegliere se si desidera ascoltare le entrate, le uscite o entrambe.

   >[!NOTE]
   >
   >Tieni presente che **[!UICONTROL Enter]** e **[!UICONTROL Exit]** corrispondono agli stati di partecipazione al segmento **Realizzato** e **Uscito** da Adobe Experience Platform. Per ulteriori informazioni su come valutare un segmento, consulta la [documentazione del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

1. Seleziona uno spazio dei nomi. Questa opzione è necessaria solo se l’evento è posizionato come primo passaggio del percorso.

   ![](../assets/segment7.png)

Il payload contiene le seguenti informazioni contestuali, che è possibile utilizzare in condizioni e azioni:

* il comportamento (entrata, uscita)
* il timestamp della qualifica
* l’id segmento

Quando si utilizza l&#39;editor espressioni in una condizione o in un&#39;azione che segue un&#39;attività **[!UICONTROL Segment qualification]**, è possibile accedere al nodo **[!UICONTROL SegmentQualification]**. È possibile scegliere tra **[!UICONTROL Last qualification time]** e **[!UICONTROL status]** (entrata o uscita).

Vedi [Attività condizione](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

Un nuovo percorso che include un evento di qualificazione dei segmenti è operativo dieci minuti dopo la pubblicazione. Questo intervallo di tempo corrisponde all&#39;intervallo di aggiornamento della cache del servizio dedicato. Pertanto, è necessario attendere dieci minuti prima di utilizzare questo percorso.

## Best practice {#best-practices-segments}

L&#39;attività **[!UICONTROL Segment Qualification]** consente l&#39;ingresso immediato in percorsi di persone qualificate o non qualificate da un segmento Adobe Experience Platform.

La velocità di ricezione di queste informazioni è elevata. Le misurazioni effettuate mostrano una velocità di 10.000 eventi ricevuti al secondo. Di conseguenza, è necessario assicurarsi di capire come possono verificarsi picchi di ingresso, come evitarli e come rendere il percorso pronto per loro.

### Segmenti batch{#batch-speed-segment-qualification}

Quando utilizzi la qualificazione del segmento per un segmento batch, tieni presente che un picco di ingresso si verificherà al momento del calcolo giornaliero. La dimensione del picco dipenderà dal numero di individui che entrano (o escono) dal segmento ogni giorno.

Inoltre, se il segmento batch è stato appena creato e immediatamente utilizzato in un percorso, il primo batch di calcolo potrebbe far entrare nel percorso un numero molto elevato di individui.

### Segmenti in streaming{#streamed-speed-segment-qualification}

Quando si utilizza la qualificazione dei segmenti per i segmenti in streaming, vi è meno rischio di raggiungere picchi elevati di entrate/uscite a causa della valutazione continua del segmento. Tuttavia, se la definizione del segmento porta a rendere un grande volume di clienti idonei allo stesso tempo, potrebbe esserci anche un picco.

Per ulteriori informazioni sulla segmentazione in streaming, consulta questa [pagina](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### Come evitare gli overload{#overloads-speed-segment-qualification}

Di seguito sono riportate alcune best practice che aiuteranno a evitare il sovraccarico dei sistemi utilizzati nei percorsi (origini dati, azioni personalizzate, azioni Adobe Campaign Standard).

Non utilizzare in un&#39;attività **[!UICONTROL Segment Qualification]** un segmento batch immediatamente dopo la sua creazione. Eviterà il picco del primo calcolo. Se stai per utilizzare un segmento che non è mai stato calcolato, nell’area di lavoro del percorso verrà visualizzato un avviso giallo.

![](../assets/segment-error.png)

Imposta una regola di limite per le origini dati e le azioni utilizzate nei percorsi per evitare di sovraccaricarle (consulta questa [sezione](../api/capping.md)). La regola di limite non ha alcun nuovo tentativo. Se è necessario riprovare, è necessario utilizzare un percorso alternativo nel percorso selezionando la casella **[!UICONTROL Add an alternative path in case of a timeout or an error]** in condizioni o azioni.

Prima di utilizzare il segmento in un percorso di produzione, valuta sempre il volume di singoli utenti che si qualificano quotidianamente per questo segmento. A tale scopo, è possibile controllare la sezione **[!UICONTROL Segments]** in Adobe Experience Platform e guardare il grafico sul lato destro.

![](../assets/segment-overload.png)
