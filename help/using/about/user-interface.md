---
title: Interfaccia utente
description: Ulteriori informazioni sull’interfaccia utente
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 3c6c20feb2d461a5780dde5539811beee2eb78b7
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 90%

---


# Interfaccia utente{#concept_rcq_lqt_52b}

>[!NOTE]
>
>Per ottenere il meglio da [!DNL Journey Orchestration], ti consigliamo di utilizzare Chrome come browser Internet. L’interfaccia viene visualizzata nella lingua definita all’interno di IMS. Se la lingua IMS non è supportata da [!DNL Journey Orchestration], l’interfaccia viene visualizzata in inglese.
>
>Questa documentazione viene spesso aggiornata per riflettere le recenti modifiche apportate al prodotto. Tuttavia, alcune schermate possono risultare leggermente diverse dall’interfaccia del prodotto.

## Accesso a [!DNL Journey Orchestration]{#accessing_journey_orchestration}

Per accedere all’interfaccia di [!DNL Journey Orchestration], fai clic sull’icona **[!UICONTROL App Selector]** in alto a destra. Then click **[!UICONTROL Journey Orchestration]**, on the right side, below **[!UICONTROL Experience Platform]**.

![](../assets/journey1.png)

Puoi anche accedere a [!DNL Journey Orchestration] dalla home page di Experience Cloud, nella sezione **[!UICONTROL Quick access]**.

![](../assets/journey1bis.png)

## Esplorazione dell’interfaccia{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="Informazioni sull’elenco percorsi"
>abstract="L’elenco dei percorsi ti consente di visualizzarli tutti in contemporanea, di visionarne lo stato ed eseguire le azioni di base. Puoi duplicare, interrompere o eliminare i tuoi percorsi. A seconda del percorso, alcune azioni potrebbero non essere disponibili. Ad esempio, non puoi eliminare o riavviare un percorso terminato. È possibile creare una nuova versione oppure duplicarla. Puoi anche usare la barra di ricerca per cercare un percorso."
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="Guarda il video dimostrativo"

I menu superiori ti consentono di navigare tra le diverse funzionalità di [!DNL Journey Orchestration]: **[!UICONTROL Home]** (i percorsi), **[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Per visualizzare l’aiuto contestuale, fai clic sull’icona ![](../assets/icon-context.png) posta nell’angolo in alto a destra dello schermo. È disponibile nelle diverse schermate di elenco di [!DNL Journey Orchestration] (percorsi, eventi, azioni e origini dati). In tal modo, puoi visualizzare una descrizione rapida delle funzionalità correnti e accedere agli articoli e ai video correlati.

![](../assets/journey2bis.png)

## Ricerca e filtro{#section_lgm_hpz_pgb}

Negli elenchi **[!UICONTROL Home]**,**[!UICONTROL Data Sources]** **[!UICONTROL Events]** e **[!UICONTROL Actions]**, una barra di ricerca consente di effettuare la ricerca di un elemento.

Per accedere a **[!UICONTROL Filters]**, fai clic sull’icona del filtro posta in alto a sinistra nell’elenco. Il menu dei filtri ti consente di filtrare gli elementi visualizzati in base a criteri diversi. Puoi scegliere di visualizzare solo gli elementi di un determinato tipo o stato, quelli creati oppure quelli modificati negli ultimi 30 giorni.

Negli elenchi **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** e **[!UICONTROL Actions]**, utilizza **[!UICONTROL Creation filters]** (Filtri di creazione)  per filtrare in base alla data e all’utente di creazione. Ad esempio, puoi scegliere di visualizzare solo gli eventi creati negli ultimi 30 giorni.

Nell’elenco dei percorsi (sotto **[!UICONTROL Home]**), oltre a **[!UICONTROL Creation filters]**, puoi anche filtrare i percorsi visualizzati in base allo stato e alla versione (**[!UICONTROL Status and version filters]**). È inoltre possibile scegliere di visualizzare solo i percorsi che utilizzano un evento, un gruppo di campi o un’azione particolare (**[!UICONTROL Activity filters]** e **[!UICONTROL Data filters]**). **[!UICONTROL Publication filters]** ti consente di selezionare una data di pubblicazione o un utente. Ad esempio, puoi scegliere di visualizzare solo le versioni più recenti dei percorsi live pubblicate ieri. A questo proposito, consulta la sezione [](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Le colonne visualizzate possono essere personalizzate utilizzando il pulsante di configurazione, posto in alto a destra degli elenchi. La personalizzazione viene salvata per ogni utente.

Le colonne **[!UICONTROL Last update]** e **[!UICONTROL Last update by]** consentono di visualizzare quando si è verificato l’ultimo aggiornamento dei percorsi e quale utente li ha gestiti.

![](../assets/journey74.png)

Nei riquadri di configurazione dell’evento, dell’origine dati e dell’azione, il campo **[!UICONTROL Used in]** visualizza il numero di percorsi che utilizzano quel particolare evento, il gruppo di campi o l’azione. Per visualizzare l’elenco dei percorsi corrispondenti, puoi fare clic sul pulsante **[!UICONTROL View journeys]**.

![](../assets/journey3bis.png)

All’interno dei vari elenchi, puoi eseguire le azioni di base su ciascun elemento. Ad esempio, è possibile duplicare o eliminare un elemento.

![](../assets/journey4.png)

## Esplorazione dei campi di Adobe Experience Platform {#friendly-names-display}

Quando si definisce il [payload dell’evento](../event/defining-the-payload-fields.md) e il [payload del gruppo di campi](../datasource/field-groups.md) e si selezionano i campi nell’[editor delle espressioni](../expression/expressionadvanced.md), oltre al nome del campo viene mostrato anche il nome visualizzato. Queste informazioni vengono recuperate dalla definizione dello schema di Experience Data Model.

Se durante la configurazione degli schemi vengono forniti descrittori come &quot;xdm:alternateDisplayInfo&quot;, i nomi descrittivi sostituiranno i nomi visualizzati. Questa funzione risulta particolarmente utile quando si lavora con &quot;eVar&quot; e campi generici. È possibile configurare i descrittori di nomi descrittivi tramite una chiamata API. Per ulteriori informazioni, consulta la [Guida per gli sviluppatori del registro dello schema](https://docs.adobe.com/content/help/it-IT/experience-platform/xdm/api/getting-started.html).

![](../assets/xdm-from-descriptors.png)

Se è disponibile un nome descrittivo, il campo verrà visualizzato come `<friendly-name>(<name>)`. Se non è disponibile alcun nome descrittivo, verrà mostrato il nome visualizzato, ad esempio `<display-name>(<name>)`. Se non è definito nessuno dei due, verrà visualizzato solo il nome tecnico del campo `<name>`.

>[!NOTE]
>
>I nomi descrittivi non vengono recuperati quando si selezionano i campi da un’unione di schemi.

## Utilizzo delle varie scelte rapide{#section_ksq_zr1_ffb}

Di seguito sono riportate le diverse scelte rapide disponibili nell’interfaccia di [!DNL Journey Orchestration].

_Nell’elenco dei percorsi, delle azioni, delle origini dati o degli eventi:_

* Premi **c** per creare un nuovo percorso, azione, origine dati o evento.

_Durante la configurazione di un’attività in un percorso:_

L’area di lavoro viene salvata automaticamente. Nella parte superiore sinistra dell’area di lavoro è riportato lo stato di salvataggio.

* Premi **Esc** per chiudere il riquadro di configurazione ed eliminare le modifiche apportate. Equivale al pulsante **[!UICONTROL Cancel]**.
* Press **Enter** or click outside the pane to close the configuration pane. Le modifiche vengono salvate. Equivale al pulsante **[!UICONTROL Ok]**.
* If you press **Delete** or **backspace**, you can then press **Enter** to confirm the deletion.

_Nei pop-up:_

* Press **escape** to close it (equivalent of the **[!UICONTROL Cancel]** button).
* Press **Enter** to save or confirm (equivalent of the **[!UICONTROL Ok]** or **[!UICONTROL Save]** button).

_Nel riquadro di configurazione dell’evento, dell’origine dati o dell’azione:_

* Premi **escape** per chiudere il riquadro di configurazione senza salvataggio.
* Press **Enter** to save modifications and close the configuration pane.
* Premi la **scheda** per spostarti tra i diversi campi da configurare.

_Nell’editor di espressioni semplici_

* Fai doppio clic su un campo a sinistra per aggiungere una query, che equivale al trascinamento.

_Durante la navigazione nei campi XDM:_

* Facendo clic su un &quot;nodo&quot; verranno selezionati tutti i campi al suo interno.

_In tutte le aree di testo:_

* Utilizza la combinazione di tasti **Ctrl/Comando + A** per selezionare il testo. Nell’anteprima del payload, seleziona il payload.

_In una schermata con una barra di ricerca:_

* Utilizza la combinazione di tasti **Ctrl/Comando + F** per selezionare la barra di ricerca.

_Nell’area di lavoro di un percorso:_

* Utilizza la combinazione di tasti **Ctrl/Comando + A** per selezionare tutte le attività.
* When one or several activities are selected, press **Delete** or **backspace** to delete them. Then you can press **Enter** to confirm in the confirmation pop-up.
* Fai doppio clic su un’attività dalla palette a sinistra per aggiungerla alla prima posizione disponibile (dall’alto verso il basso).
