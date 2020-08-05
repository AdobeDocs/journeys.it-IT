---
title: Utilizzo del designer del percorso
description: Scopri di più sull’utilizzo del designer di viaggi
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
source-git-commit: a65a5db5b35291cbc2635f9ae67fd8c8c5284575
workflow-type: tm+mt
source-wordcount: '1335'
ht-degree: 5%

---


# Utilizzo del designer del percorso {#concept_m1g_5qt_52b}

Il menu Home del viaggio consente di visualizzare l&#39; **elenco dei viaggi**. Crea un nuovo percorso o fai clic su uno esistente per aprire l&#39;interfaccia **del progettista del** percorso. Il designer è costituito dalle seguenti aree: la palette, il quadro e il riquadro di configurazione dell&#39;attività.

## La lista di viaggi {#journey_list}

The **journey list** allows you to view all your journeys at once, see their status and perform basic actions. Puoi duplicare, interrompere o eliminare i tuoi percorsi. A seconda del percorso, alcune azioni potrebbero non essere disponibili. Ad esempio, non puoi eliminare o riavviare un percorso terminato. Potete creare una nuova versione, duplicarla o interromperla. Puoi anche usare la barra di ricerca per cercare un percorso.

Per accedere a **[!UICONTROL Filters]**, fai clic sull’icona del filtro posta in alto a sinistra nell’elenco. Il menu dei filtri consente di filtrare i viaggi visualizzati in base a criteri diversi (stato, quelli creati, quelli modificati negli ultimi 30 giorni, solo le versioni più recenti, ecc.). Potete anche scegliere di visualizzare solo i viaggi che utilizzano un evento, un gruppo di campi o un&#39;azione particolare. È possibile configurare le colonne visualizzate nell&#39;elenco. Tutti i filtri e le colonne vengono salvati per utente.

![](../assets/journey74.png)

Tutte le versioni dei viaggi vengono visualizzate nell’elenco con il numero di versione. A questo proposito, consulta la sezione [](../building-journeys/journey-versions.md).

![](../assets/journey37.png)

>[!NOTE]
>
>Per aprire il quadro di un viaggio in un&#39;altra scheda del browser, tieni premuto il tasto **Ctrl** o **Comando** e fai clic sul percorso.

## La palette {#palette}

La **palette** si trova sul lato sinistro dello schermo. Tutte le attività disponibili sono suddivise in diverse categorie: **[!UICONTROL Events]**, **[!UICONTROL Orchestration]** e **[!UICONTROL Actions]**. Potete espandere o comprimere le diverse categorie facendo clic sul loro nome. Per utilizzare un’attività nel viaggio, trascinatela dalla palette al quadro. È inoltre possibile fare doppio clic su un&#39;attività nella palette per aggiungerla all&#39;area di lavoro, al passaggio successivo disponibile. È necessario configurare ogni attività aggiunta dalla palette prima di pubblicare il percorso. Se rilasci un&#39;attività nell&#39;area di lavoro e non ne finisci la configurazione, rimarrà nell&#39;area di lavoro, ma un avviso rosso indicherà che la configurazione non è terminata per questa attività.

>[!NOTE]
>
>Notate che ci sono delle regole quando si configura un viaggio. La configurazione non consentita verrà scartata. Ad esempio, non potete mettere in parallelo delle azioni, collegare un&#39;attività a un passaggio precedente per creare un ciclo, avviare un percorso con qualcos&#39;altro rispetto a un evento, ecc.

![](../assets/journey38.png)

The **[!UICONTROL Show disabled items]** icon in the top left corner allows you to hide or display unavailable elements in the palette, for example the events that use a different namespace than the ones used in your journey. Per impostazione predefinita, gli elementi non disponibili sono nascosti. Se scegli di visualizzarli, verranno visualizzati in grigio.

Quando si utilizza il **[!UICONTROL Search]** campo, il numero di risultati viene visualizzato per ogni categoria di attività canvas.

![](../assets/palette-filter.png)

## Il quadro {#canvas}

Il **quadro** è la zona centrale del designer di viaggi. È in questa zona che puoi rilasciare le tue attività e configurarle. Fate clic su un&#39;attività nell&#39;area di lavoro per configurarla. Viene aperto il riquadro di configurazione dell&#39;attività sul lato destro. Potete ingrandire e ridurre utilizzando i pulsanti &quot;+&quot; e &quot;-&quot; in alto a destra. Nell’area di lavoro, tutte le attività consentono di aggiungere un passaggio successivo, tranne **[!UICONTROL End]** le attività (vedere [](../building-journeys/end-activity.md)).

![](../assets/journey39.png)

## Riquadro di configurazione dell&#39;attività {#configuration_pane}

Il riquadro **di configurazione dell&#39;** attività viene visualizzato quando si fa clic su un&#39;attività nella palette. Compila i campi richiesti. Fate clic sull&#39; **[!UICONTROL Delete]** icona per eliminare l&#39;attività. Fate clic su **[!UICONTROL Cancel]** per annullare le modifiche o **[!UICONTROL Ok]** per confermare. Per eliminare le attività, potete anche selezionare una (o più) attività e premere il tasto Backspace. Premere il tasto Escape per chiudere il riquadro di configurazione dell&#39;attività.

Nell’area di lavoro, le attività dell’azione e dell’evento sono rappresentate da un’icona con il nome dell’evento o dell’azione visualizzato sotto. Nel riquadro di configurazione dell&#39;attività, potete utilizzare il **[!UICONTROL Label]** campo per aggiungere un suffisso al nome dell&#39;attività. Queste etichette consentiranno di contestualizzare l&#39;uso di eventi e azioni, soprattutto quando durante il viaggio si utilizza più volte lo stesso evento o azione. Potrete inoltre visualizzare le etichette aggiunte nel [!DNL Journey Orchestration] rapporto.

![](../assets/journey59bis.png)

## Azioni nella barra superiore {#top_actions}

A seconda dello stato del viaggio, puoi eseguire diverse azioni sul viaggio utilizzando i pulsanti disponibili nell’angolo in alto a destra: **[!UICONTROL Publish]**, **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**, **[!UICONTROL Journey properties]**, **[!UICONTROL Test]**. Questi pulsanti vengono visualizzati quando non è selezionata alcuna attività. Alcuni pulsanti verranno visualizzati in modo contestuale. Il pulsante del registro della modalità di prova viene visualizzato quando la modalità di prova è attivata (vedere [](../building-journeys/testing-the-journey.md)). Il pulsante di segnalazione viene visualizzato quando il viaggio è live, interrotto o chiuso.

![](../assets/journey41.png)

## Utilizzo dei percorsi nel quadro {#paths}

Diverse attività (**[!UICONTROL Condition]**, **[!UICONTROL Action]** attività) consentono di definire un&#39;azione di fallback in caso di errore o timeout. Nel riquadro di configurazione dell&#39;attività, selezionate la casella: **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Un altro percorso viene aggiunto dopo l&#39;attività. La durata di timeout è definita nelle proprietà del percorso (vedete [](../building-journeys/changing-properties.md) da un utente amministratore. Ad esempio, se l’invio di un messaggio e-mail richiede troppo tempo o si verifica un errore, potete decidere di inviare un SMS.

![](../assets/journey42.png)

Diverse attività (evento, azione, attesa) consentono di aggiungere diversi percorsi dopo di esse. A questo scopo, posizionate il cursore sull&#39;attività e fate clic sul simbolo &quot;+&quot;. Solo le attività di evento e di attesa possono essere impostate in parallelo. Se più eventi sono impostati in parallelo, il percorso scelto sarà quello del primo evento che si verifica.

Quando ascoltate un evento, vi consigliamo di non attendere l’evento a tempo indeterminato. Non è obbligatorio, è solo una buona pratica. Se si desidera ascoltare uno o più eventi solo durante un certo periodo di tempo, si posizionano uno o più eventi e un&#39;attività di attesa in parallelo. A questo proposito, consulta la sezione [](../building-journeys/event-activities.md#section_vxv_h25_pgb).

Per eliminare il percorso, posizionate il cursore su di esso e fate clic sull’ **[!UICONTROL Delete arrow]** icona .

![](../assets/journey42ter.png)

Nel quadro, quando due attività vengono disconnesse, viene visualizzato un avviso. Posizionare il cursore sull&#39;icona di avviso per visualizzare il messaggio di errore. Per risolvere il problema, spostate semplicemente l&#39;attività disconnessa e collegatela all&#39;attività precedente.

![](../assets/canvas-disconnected.png)

## Copia e incolla delle attività {#copy-paste}

Potete copiare una o più attività di un viaggio e incollarle nello stesso percorso o in un altro. Questo consente di risparmiare tempo se desiderate riutilizzare numerose attività già configurate in un viaggio precedente.

**Note importanti**

* Potete copiare/incollare diverse schede e browser. Potete copiare/incollare solo le attività all’interno della stessa istanza.
* Non è possibile copiare/incollare un evento se il percorso di destinazione ha un evento che utilizza uno spazio nomi diverso.
* Le attività incollate possono fare riferimento a dati che non esistono nel percorso di destinazione, ad esempio se copiate/incollate tra diverse sandbox. Verificate sempre la presenza di errori ed effettuate le regolazioni necessarie.
* Non è possibile annullare un’azione. Per eliminare le attività incollate, dovrete selezionarle ed eliminarle. Accertatevi quindi di selezionare solo le attività necessarie prima di copiarle.
* Potete copiare le attività da qualsiasi viaggio, anche da quelle in sola lettura.
* Potete selezionare qualsiasi attività, anche quelle non collegate. Le attività collegate resteranno collegate dopo essere state incollate.

Di seguito sono riportati i passaggi per copiare/incollare le attività:

1. Apri un viaggio.
1. Selezionate le attività da copiare spostando il mouse mentre fate clic. Potete anche fare clic su ogni attività mentre premete il tasto **Ctrl/Comando** . Utilizzate **Ctrl/Comando + A** per selezionare tutte le attività.
   ![](../assets/copy-paste1.png)
1. Premere **Ctrl/Comando + C**.
Se desiderate copiare una sola attività, potete fare clic su di essa e utilizzare l&#39;icona **Copia** in alto a sinistra nel riquadro di configurazione dell&#39;attività.
   ![](../assets/copy-paste2.png)
1. In qualsiasi percorso, premere **Ctrl/Comando + V** per incollare le attività senza collegarle a un nodo esistente. Le attività incollate vengono collocate nello stesso ordine. Dopo essere state incollate, le attività restano selezionate in modo da poterle spostare facilmente. È inoltre possibile posizionare il cursore su un segnaposto vuoto e premere **Ctrl/Comando + V**. Le attività inviate saranno collegate al nodo.
   ![](../assets/copy-paste3.png)

