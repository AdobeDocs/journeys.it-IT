---
title: Interfaccia utente
description: Ulteriori informazioni sull'interfaccia utente
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 891216a489b79fe4b168ecdb6120f5d9f3e107d0

---


# Interfaccia utente{#concept_rcq_lqt_52b}


>[!CONTEXTUALHELP]
>id=&quot;jo_home&quot;
>title=&quot;Informazioni sull&#39;elenco dei viaggi&quot;
>abstract=&quot;L’elenco dei viaggi consente di visualizzare tutti i viaggi contemporaneamente, visualizzarne lo stato ed eseguire le azioni di base. Puoi duplicare, interrompere o eliminare i tuoi viaggi. A seconda del percorso, alcune azioni potrebbero non essere disponibili. Ad esempio, non puoi interrompere o eliminare un viaggio completato. Puoi anche usare la barra di ricerca per cercare un viaggio.&quot;
>Additional-url=&quot;https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4&quot; text=&quot;Guarda il video dimostrativo&quot;

>[!NOTE]
>
>Per ottenere il meglio da Journey Orchestration, si consiglia di utilizzare Chrome come il vostro browser Internet.
>
>Questa documentazione viene spesso aggiornata per riflettere le recenti modifiche apportate al prodotto. Tuttavia, alcune schermate possono essere leggermente diverse dall&#39;interfaccia del prodotto.

## Esplorazione dell’interfaccia{#section_jsq_zr1_ffb}

Per accedere all&#39;interfaccia dell&#39;orchestrazione del viaggio, fare clic sull&#39; **[!UICONTROL App Selector]** icona in alto a destra. Quindi fate clic **[!UICONTROL Journey Orchestration]**, a destra, sotto &quot;Experience Platform&quot;.

![](../assets/journey1.png)

Puoi anche accedere all’orchestrazione del percorso dalla home page di Experience Cloud, nella **[!UICONTROL Quick access]** sezione.

![](../assets/journey1bis.png)

I menu superiori consentono di navigare tra le diverse funzionalità dell&#39;Orchestrazione del viaggio: **[!UICONTROL Home]**(i viaggi),**[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Fate clic sull&#39; ![](../assets/icon-context.png) icona nell&#39;angolo superiore destro dello schermo per visualizzare la guida contestuale. È disponibile nelle diverse schermate dell&#39;elenco di orchestrazione del viaggio (viaggi, eventi, azioni e origini dati). Questo consente di visualizzare una descrizione rapida delle funzionalità correnti e di accedere agli articoli e ai video correlati.

![](../assets/journey2bis.png)

## Ricerca e filtro{#section_lgm_hpz_pgb}

Negli **[!UICONTROL Home]**,**[!UICONTROL Data Sources]** elenchi **[!UICONTROL Events]** e **[!UICONTROL Actions]** negli elenchi, una barra di ricerca consente di cercare un elemento.

Per **[!UICONTROL Filters]** accedervi, fate clic sull’icona del filtro in alto a sinistra nell’elenco. Il menu dei filtri consente di filtrare gli elementi visualizzati in base a criteri diversi. Potete scegliere di visualizzare solo gli elementi di un determinato tipo o stato, quelli creati o quelli modificati negli ultimi 30 giorni.

Negli **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** e **[!UICONTROL Actions]** negli elenchi, utilizzate i filtri **** Creazione per filtrare in base alla data e all’utente di creazione. Ad esempio, potete scegliere di visualizzare solo gli eventi creati negli ultimi 30 giorni.

Nell&#39;elenco dei viaggi (sotto **[!UICONTROL Home]**), oltre al **[!UICONTROL Creation filters]**, puoi anche filtrare i viaggi visualizzati in base al loro stato e alla loro versione (**[!UICONTROL Status and version filters]**). È inoltre possibile scegliere di visualizzare solo i viaggi che utilizzano un evento, un gruppo di campi o un&#39;azione particolare (**[!UICONTROL Activity filters]** e **[!UICONTROL Data filters]**). **[!UICONTROL Publication filters]** Consente di selezionare una data di pubblicazione o un utente. Ad esempio, potete scegliere di visualizzare solo le versioni più recenti dei viaggi live pubblicate ieri. Vedere [](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Le colonne visualizzate possono essere personalizzate utilizzando il pulsante di configurazione in alto a destra degli elenchi. La personalizzazione viene salvata per ogni utente.

Le colonne **[!UICONTROL Last update]** e **[!UICONTROL Last update by]** consentono di visualizzare quando si è verificato l’ultimo aggiornamento dei viaggi e quale utente li ha gestiti.

![](../assets/journey74.png)

Nei riquadri di configurazione dell&#39;evento, dell&#39;origine dati e dell&#39;azione, il **[!UICONTROL Used in]** campo visualizza il numero di viaggi che utilizzano quel particolare evento, gruppo di campi o azione. Potete fare clic sul **[!UICONTROL View journeys]** pulsante per visualizzare l’elenco dei percorsi corrispondenti.

![](../assets/journey3bis.png)

Nei diversi elenchi, potete eseguire azioni di base su ciascun elemento. Ad esempio, potete duplicare o eliminare un elemento.

![](../assets/journey4.png)

## Esplorazione dei campi della piattaforma dati {#friendly-names-display}

Quando si definisce il payload [dell&#39;](../event/defining-the-payload-fields.md)evento, il payload [del gruppo di](../datasource/field-groups.md) campi e si selezionano i campi nell&#39;editor [delle](../expression/expressionadvanced.md)espressioni, oltre al nome del campo viene visualizzato anche il nome visualizzato. Queste informazioni vengono recuperate dalla definizione dello schema nel modello dati esperienza.

Se durante la configurazione degli schemi vengono forniti descrittori come &quot;xdm:alternateDisplayInfo&quot;, i nomi descrittivi sostituiranno i nomi visualizzati. È particolarmente utile quando si lavora con &quot;eVars&quot; e campi generici. È possibile configurare descrittori di nomi descrittivi descrittivi tramite una chiamata API. Per ulteriori informazioni, vedere la guida [per gli sviluppatori del Registro di](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/schema_registry_developer_guide.md)schema.

![](../assets/xdm-from-descriptors.png)

Se è disponibile un nome descrittivo, il campo verrà visualizzato come `<friendly-name>(<name>)`. Se non è disponibile alcun nome descrittivo, ad esempio `<display-name>(<name>)`, verrà visualizzato il nome visualizzato. Se non ne viene definita alcuna, verrà visualizzato solo il nome tecnico del campo `<name>`.

>[!NOTE]
>
>I nomi descrittivi non vengono recuperati quando si selezionano campi da un&#39;unione di schemi.

## Utilizzo dei diversi collegamenti{#section_ksq_zr1_ffb}

Di seguito sono riportati i diversi collegamenti disponibili nell&#39;interfaccia dell&#39;orchestrazione del viaggio.

_Nell&#39;elenco dei viaggi, delle azioni, delle origini dati o degli eventi:_

* Premere **c** per creare un nuovo percorso, azione, origine dati o evento.

_Durante la configurazione di un&#39;attività in un percorso:_

Il quadro viene salvato automaticamente. Nella parte superiore sinistra del quadro è riportato lo stato di salvataggio.

* Premere **Esc** per chiudere il riquadro di configurazione ed eliminare le modifiche apportate. Equivale al **[!UICONTROL Cancel]** pulsante.
* Premere **[!UICONTROL Enter]** o fare clic all&#39;esterno del riquadro per chiudere il riquadro di configurazione. Le modifiche vengono salvate. Equivale al **[!UICONTROL Ok]** pulsante.
* Se si preme **[!UICONTROL Delete]** o **backspace**, è possibile premere **[!UICONTROL Enter]** per confermare l&#39;eliminazione.

_Nei pop-up:_

* Premere **escape** per chiuderlo (equivalente al pulsante **Annulla** ).
* Premere **[!UICONTROL Enter]** per salvare o confermare (equivalente al **[!UICONTROL Ok]** pulsante o **[!UICONTROL Save]** ).

_Nel riquadro di configurazione dell&#39;evento, dell&#39;origine dati o dell&#39;azione:_

* Premere **escape** per chiudere il riquadro di configurazione senza salvare.
* Premere **[!UICONTROL Enter]** per salvare le modifiche e chiudere il riquadro di configurazione.
* Premere **scheda** per passare ai diversi campi da configurare.

_Nell&#39;editor di espressioni semplici_

* Fate doppio clic su un campo, a sinistra, per aggiungere una query (equivalente a trascinamento).

_Durante la navigazione nei campi XDM:_

* Selezionando un &quot;nodo&quot; verranno selezionati tutti i campi del nodo.

_In tutte le aree di testo:_

* Utilizzare la combinazione di tasti **Ctrl/Comando + A** per selezionare il testo. Nell&#39;anteprima del payload, seleziona il payload.

_In una schermata con una barra di ricerca:_

* Utilizzate la combinazione di tasti **Ctrl/Comando + F** per selezionare la barra di ricerca.

_Nel quadro di un viaggio:_

* Utilizzate la combinazione di tasti **Ctrl/Comando + A** per selezionare tutte le attività.
* Quando si selezionano una o più attività, premere **[!UICONTROL Delete]** o **backspace** per eliminarle. Quindi potete premere **[!UICONTROL Enter]** per confermare nella finestra a comparsa di conferma.
* Fate doppio clic su un&#39;attività dalla palette a sinistra per aggiungerla alla prima posizione disponibile (dall&#39;alto verso il basso).
