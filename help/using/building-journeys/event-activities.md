---
title: Eventi attività
description: Informazioni sulle attività degli eventi
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
source-git-commit: 3937f92035651fca5ddd7f54c9b650d050f2587f
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 1%

---


# Eventi attività {#concept_rws_1rt_52b}

Gli eventi configurati dall&#39;utente tecnico (vedete [](../event/about-events.md) tutti visualizzati nella prima categoria della palette, sul lato sinistro dello schermo.

![](../assets/journey43.png)

Iniziate sempre il viaggio trascinando e rilasciando un&#39;attività dell&#39;evento. Potete anche fare doppio clic su di esso.

![](../assets/journey44.png)

Quando fate clic sull&#39;attività dell&#39;evento nell&#39;area di lavoro, viene visualizzato il riquadro di configurazione dell&#39;attività. Per impostazione predefinita, quando si utilizza lo stesso evento più volte, al nome dell&#39;evento nell&#39;area di lavoro viene aggiunto un numero incrementale. Inoltre, potete utilizzare il **[!UICONTROL Label]** campo per aggiungere un suffisso al nome dell&#39;evento che verrà visualizzato sotto l&#39;attività nell&#39;area di lavoro. Questo è utile per identificare gli eventi nel quadro, soprattutto se si utilizza più volte lo stesso evento. Inoltre, faciliterà il debug in caso di errori e faciliterà la lettura dei report.

![](../assets/journey33.png)

## Eventi generali {#section_ofg_jss_dgb}

Per questo tipo di evento, è possibile aggiungere solo un&#39;etichetta e una descrizione. Impossibile modificare il resto della configurazione. È stato eseguito dall&#39;utente tecnico. A questo proposito, consulta la sezione [](../event/about-events.md).

## Eventi di reazione {#section_dhx_gss_dgb}

Tra le diverse attività dell&#39;evento disponibili nella palette, è disponibile l&#39;evento **Reazioni** incorporato. Questa attività consente di reagire ai dati di tracciamento relativi a un messaggio inviato con e-mail, SMS o attività push nello stesso percorso. Queste informazioni provengono dai messaggi transazionali nel  Adobe Campaign Standard. Queste informazioni vengono acquisite in tempo reale nel momento in cui vengono condivise con l&#39;Platform dati. Per le notifiche push, puoi reagire ai messaggi su cui hai fatto clic, che sono stati inviati o che hanno avuto esito negativo. Per gli SMS, è possibile reagire ai messaggi inviati o non riusciti. Per le e-mail, potete reagire ai messaggi su cui è stato fatto clic, che sono stati inviati, che sono stati aperti o che hanno avuto esito negativo.

È inoltre possibile utilizzare questo meccanismo per eseguire un&#39;azione in assenza di reazioni ai messaggi. A tal fine, create un secondo percorso parallelo all&#39;attività di reazione e aggiungete un&#39;attività di attesa. Se durante il periodo definito nell&#39;attività di attesa non è presente alcuna reazione, verrà scelto il secondo percorso. Potete scegliere di inviare, ad esempio, un messaggio di follow-up.

È possibile utilizzare un&#39;attività di reazione nel quadro solo se è già presente un&#39;attività e-mail, push o SMS.

See [About action activities](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Di seguito sono riportati i diversi passaggi per configurare gli eventi di reazione:

1. Aggiungete una **[!UICONTROL Label]** alla reazione. Questo passaggio è facoltativo.
1. Dall&#39;elenco a discesa, selezionate l&#39;attività di azione a cui desiderate reagire. È possibile selezionare qualsiasi attività di azione posizionata nei passaggi precedenti del percorso.
1. A seconda dell’azione selezionata (e-mail, SMS o notifica push), scegliete a cosa rispondere.
1. È possibile definire una condizione come passaggio facoltativo. Ad esempio, dopo un’azione e-mail, potete decidere di creare due percorsi, uno con un evento di reazione per monitorare i clic solo per i clienti VIP e uno con un evento di reazione per monitorare i clic eseguiti dalle donne.

>[!NOTE]
>
>Gli eventi di reazione funzionano con  Adobe Campaign Standard, sia che sia distribuito sui server AWS o Azure.
>
>Gli eventi di reazione non possono tenere traccia delle azioni e-mail, SMS o push che avvengono in un percorso diverso.
>
>Gli eventi di reazione tengono traccia dei clic sui collegamenti di tipo &quot;tracciati&quot; (vedere questa [pagina](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Non vengono presi in considerazione i collegamenti di annullamento sottoscrizione e di pagina mirror.

>[!IMPORTANT]
>
>I client e-mail come Gmail consentono il blocco delle immagini. Le aperture e-mail vengono tracciate utilizzando un’immagine di 0 pixel inclusa nel messaggio e-mail. Se le immagini sono bloccate, le aperture e-mail non verranno prese in considerazione.

## Eventi di qualifica del segmento {#segment-qualification}

Questa attività consente al tuo viaggio di ascoltare le entrate e le uscite dei profili nei segmenti Platform per far entrare o far avanzare gli individui in un viaggio. Per ulteriori informazioni sulla creazione dei segmenti, consulta questa [sezione](../segment/about-segments.md).

Supponiamo che tu abbia un segmento &quot;cliente argento&quot;. Con questa attività, puoi far entrare tutti i nuovi clienti in argento in un viaggio e inviare loro una serie di messaggi personalizzati.

Questo tipo di evento può essere posizionato come primo passo o successivo del viaggio.

Se il segmento viene trasmesso in streaming con l&#39;opzione Pubblico ad alta frequenza di Platform, l&#39;ingresso e l&#39;uscita vengono ascoltati in tempo reale. Se il segmento non è in streaming, le entrate e le uscite vengono prese in considerazione al momento del calcolo del segmento.

1. Spiega la categoria **Eventi** e rilascia un’attività di qualificazione **** Segmento nel quadro.

   ![](../assets/segment5.png)

1. Aggiungete un&#39; **etichetta** all&#39;attività. Questo passaggio è facoltativo.

1. Fai clic nel campo **Segmento** e seleziona i segmenti da sfruttare.

   ![](../assets/segment6.png)

1. Nel campo **Comportamento** , scegliere se si desidera ascoltare le entrate, le uscite o entrambi del segmento.

1. Selezionare uno spazio nomi. Questo è necessario solo se l&#39;evento è posizionato come primo passo del viaggio.

   ![](../assets/segment7.png)

Il payload contiene le seguenti informazioni contestuali, che potete utilizzare in condizioni e azioni:

* il comportamento (entrata, uscita)
* la marca temporale della qualifica
* l’ID del segmento

Quando si utilizza l&#39;editor di espressioni in una condizione o in un&#39;azione che segue un&#39;attività di qualificazione **del** segmento, è possibile accedere al nodo **SegmentQualified** . È possibile scegliere tra l&#39;ora **dell&#39;** ultima qualifica e lo **stato** (immettere o uscire).

Consultate Attività [](../building-journeys/condition-activity.md#about_condition)Condizione.

![](../assets/segment8.png)

## Utilizzo avanzato: eventi con attesa parallela{#section_vxv_h25_pgb}

**Come si può ascoltare un evento solo durante un certo periodo di tempo?**

Un&#39;attività dell&#39;evento posizionata nel percorso ascolta gli eventi in modo indefinito. Per ascoltare un evento solo durante un certo periodo di tempo, dovete aggiungere un&#39;attività di attesa parallela al percorso dell&#39;evento. Il viaggio quindi ascolterà l&#39;evento durante il tempo specificato nell&#39;attività di attesa. Se un evento viene ricevuto durante tale periodo, la persona scorre nel percorso dell&#39;evento. In caso contrario, il cliente si troverà nel percorso di attesa.

Ad esempio, hai inviato una prima notifica di benvenuto a un cliente e vuoi inviare una notifica push con sconto per il pasto solo se il cliente entra nel ristorante entro le prossime 6 ore. A questo scopo, creerete un secondo percorso (parallelo all&#39;evento ristorante uno) con un&#39;attività di attesa di 6 ore. Se l&#39;evento del ristorante viene ricevuto meno di 6 ore dopo il push di benvenuto, l&#39;attività push di sconto del pasto viene inviata. Se non viene ricevuto alcun evento ristorante entro le prossime 6 ore, la persona scorre attraverso il percorso di attesa.

![](../assets/journeyuc2_31.png)
