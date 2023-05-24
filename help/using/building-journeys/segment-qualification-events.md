---
product: adobe campaign
title: Eventi di qualificazione dei segmenti
description: Scopri gli eventi di qualificazione dei segmenti
feature: Journeys
role: User
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 5%

---

# Eventi di qualificazione dei segmenti {#segment-qualification}

## Informazioni sugli eventi di qualificazione dei segmenti{#about-segment-qualification}

Questa attività consente al percorso di monitorare gli ingressi e le uscite dei profili nei segmenti Adobe Experience Platform per consentire a singoli utenti di entrare o proseguire in un percorso. Per ulteriori informazioni sulla creazione dei segmenti, consulta questa [sezione](../segment/about-segments.md).

Supponiamo che tu abbia un segmento &quot;cliente silver&quot;. Con questa attività, puoi fare in modo che tutti i nuovi clienti silver entrino in un percorso e inviino loro una serie di messaggi personalizzati.

Questo tipo di evento può essere posizionato come primo passaggio o successivamente nel percorso.

>[!IMPORTANT]
>
>Tieni presente che i segmenti di Adobe Experience Platform vengono calcolati una volta al giorno (**batch** segmenti) o in tempo reale (**streaming** segmenti, utilizzando l’opzione Tipi di pubblico ad alta frequenza di Adobe Experience Platform).
>
>Se il segmento selezionato viene inviato in streaming, i singoli utenti appartenenti a questo segmento potrebbero entrare nel percorso in tempo reale. Se il segmento è batch, le persone appena qualificate per questo segmento potrebbero entrare nel percorso quando il calcolo del segmento viene eseguito su Adobe Experience Platform.


1. Espandi la **[!UICONTROL Events]** categoria e rilascia una **[!UICONTROL Segment qualification]** attività nell’area di lavoro.

   ![](../assets/segment5.png)

1. Aggiungi un **[!UICONTROL Label]** all’attività. Questo passaggio è facoltativo.

1. Fai clic su nella **[!UICONTROL Segment]** e selezionare i segmenti da sfruttare.

   >[!NOTE]
   >
   >Si noti che è possibile personalizzare le colonne visualizzate nell&#39;elenco e ordinarle.

   ![](../assets/segment6.png)

   Una volta aggiunto il segmento, il **[!UICONTROL Copy]** consente di copiarne nome e ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. In **[!UICONTROL Behaviour]** , scegliere se si desidera ascoltare le entrate, le uscite o entrambe.

   >[!NOTE]
   >
   >Tieni presente che **[!UICONTROL Enter]** e **[!UICONTROL Exit]** corrisponde al **Realizzato** e **Uscita** gli stati di partecipazione ai segmenti da Adobe Experience Platform. Per ulteriori informazioni su come valutare un segmento, consulta [Documentazione del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

1. Seleziona uno spazio dei nomi. Questa opzione è necessaria solo se l’evento è posizionato come primo passaggio del percorso.

   ![](../assets/segment7.png)

Il payload contiene le seguenti informazioni contestuali, che è possibile utilizzare in condizioni e azioni:

* il comportamento (entrata, uscita)
* il timestamp della qualifica
* l’id segmento

Quando si utilizza l’editor di espressioni in una condizione o azione che segue un **[!UICONTROL Segment qualification]** attività, puoi accedere al **[!UICONTROL SegmentQualification]** nodo. È possibile scegliere tra **[!UICONTROL Last qualification time]** e **[!UICONTROL status]** (entrata o uscita).

Consulta [Attività condizione](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

Un nuovo percorso che include un evento di qualificazione dei segmenti è operativo dieci minuti dopo la pubblicazione. Questo intervallo di tempo corrisponde all&#39;intervallo di aggiornamento della cache del servizio dedicato. Pertanto, è necessario attendere dieci minuti prima di utilizzare questo percorso.

## Best practice {#best-practices-segments}

Il **[!UICONTROL Segment Qualification]** L&#39;attività consente l&#39;ingresso immediato in percorsi di persone che si qualificano o squalificano da un segmento Adobe Experience Platform.

La velocità di ricezione di queste informazioni è elevata. Le misurazioni effettuate mostrano una velocità di 10.000 eventi ricevuti al secondo. Di conseguenza, è necessario assicurarsi di capire come possono verificarsi picchi di ingresso, come evitarli e come rendere il percorso pronto per loro.

### Segmenti batch{#batch-speed-segment-qualification}

Quando utilizzi la qualificazione del segmento per un segmento batch, tieni presente che un picco di ingresso si verificherà al momento del calcolo giornaliero. La dimensione del picco dipenderà dal numero di individui che entrano (o escono) dal segmento ogni giorno.

Inoltre, se il segmento batch è stato appena creato e immediatamente utilizzato in un percorso, il primo batch di calcolo potrebbe far entrare nel percorso un numero molto elevato di individui.

### Segmenti in streaming{#streamed-speed-segment-qualification}

Quando si utilizza la qualificazione dei segmenti per i segmenti in streaming, vi è meno rischio di raggiungere picchi elevati di entrate/uscite a causa della valutazione continua del segmento. Tuttavia, se la definizione del segmento porta a rendere un grande volume di clienti idonei allo stesso tempo, potrebbe esserci anche un picco.

Per ulteriori informazioni sulla segmentazione in streaming, consulta questa [pagina](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### Come evitare gli overload{#overloads-speed-segment-qualification}

Di seguito sono riportate alcune best practice che aiuteranno a evitare il sovraccarico dei sistemi utilizzati nei percorsi (origini dati, azioni personalizzate, azioni Adobe Campaign Standard).

Non utilizzare, in un **[!UICONTROL Segment Qualification]** attività, un segmento batch immediatamente dopo la sua creazione. Eviterà il picco del primo calcolo. Se stai per utilizzare un segmento che non è mai stato calcolato, nell’area di lavoro del percorso verrà visualizzato un avviso giallo.

![](../assets/segment-error.png)

Inserisci una regola di limite per le origini dati e le azioni utilizzate nei percorsi per evitare di sovraccaricarle (consulta questa sezione [sezione](../api/capping.md)). La regola di limite non ha alcun nuovo tentativo. Se devi riprovare, seleziona la casella e usa un percorso alternativo nel percorso **[!UICONTROL Add an alternative path in case of a timeout or an error]** in condizioni o azioni.

Prima di utilizzare il segmento in un percorso di produzione, valuta sempre il volume di singoli utenti che si qualificano quotidianamente per questo segmento. A questo scopo, puoi controllare il **[!UICONTROL Segments]** in Adobe Experience Platform e osserva il grafico sul lato destro.

![](../assets/segment-overload.png)
