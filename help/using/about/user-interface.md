---
product: adobe campaign
title: Interfaccia utente
description: Ulteriori informazioni sull’interfaccia utente
feature: Journeys
role: User
level: Intermediate
exl-id: 0d0e74c7-6cb0-4068-a69a-3c01f8b3552d
source-git-commit: a5ec1c4c5608113bb17dfbdea0587f6bb342099a
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 61%

---

# Interfaccia utente{#concept_rcq_lqt_52b}

>[!NOTE]
>
>Per ottenere il meglio da [!DNL Journey Orchestration], ti consigliamo di utilizzare Chrome come browser Internet. L’interfaccia viene visualizzata nella lingua definita all’interno di IMS. Se la lingua IMS non è supportata da [!DNL Journey Orchestration], l’interfaccia viene visualizzata in inglese.
>
>Questa documentazione viene spesso aggiornata per riflettere le recenti modifiche apportate al prodotto. Tuttavia, alcune schermate possono risultare leggermente diverse dall’interfaccia del prodotto.

## Accesso a [!DNL Journey Orchestration]{#accessing_journey_orchestration}

Per accedere all&#39;interfaccia di [!DNL Journey Orchestration], fai clic sull&#39;icona **[!UICONTROL App Selector]** in alto a destra, quindi fai clic su **[!UICONTROL Journey Orchestration]**.

![](../assets/journey1.png)

Puoi anche accedere a [!DNL Journey Orchestration] dalla home page di Experience Cloud, nella sezione **[!UICONTROL Quick access]**.

![](../assets/journey1bis.png)

## Esplorazione dell’interfaccia{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="Informazioni sull’elenco percorsi"
>abstract="L’elenco dei percorsi ti consente di visualizzarli tutti in contemporanea, di visionarne lo stato ed eseguire le azioni di base."
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="Guarda il video dimostrativo"

I menu superiori ti consentono di navigare tra le diverse funzionalità di [!DNL Journey Orchestration]: **[!UICONTROL Home]** (i percorsi), **[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Per visualizzare l’aiuto contestuale, fai clic sull’icona ![](../assets/icon-context.png) posta nell’angolo in alto a destra dello schermo. È disponibile nelle diverse schermate di elenco di [!DNL Journey Orchestration] (percorsi, eventi, azioni e origini dati). In tal modo, puoi visualizzare una descrizione rapida delle funzionalità correnti e accedere agli articoli e ai video correlati.

![](../assets/journey2bis.png)

## Ricerca e filtro{#section_lgm_hpz_pgb}

Negli elenchi **[!UICONTROL Home]**,**[!UICONTROL Data Sources]** **[!UICONTROL Events]** e **[!UICONTROL Actions]**, una barra di ricerca consente di effettuare la ricerca di un elemento.

Per accedere a **[!UICONTROL Filters]**, fai clic sull’icona del filtro, in alto a sinistra nell’elenco. Il menu dei filtri ti consente di filtrare gli elementi visualizzati in base a criteri diversi. Puoi scegliere di visualizzare solo gli elementi di un determinato tipo o stato, quelli creati oppure quelli modificati negli ultimi 30 giorni.

Negli elenchi **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** e **[!UICONTROL Actions]**, utilizza **[!UICONTROL Creation filters]** (Filtri di creazione) per filtrare in base alla data e all’utente di creazione. Ad esempio, puoi scegliere di visualizzare solo gli eventi creati negli ultimi 30 giorni.

Nell’elenco dei percorsi (sotto **[!UICONTROL Home]**), oltre a **[!UICONTROL Creation filters]**, è anche possibile filtrare i percorsi visualizzati in base al loro stato, tipo e versione (**[!UICONTROL Status and version filters]**). Il tipo può essere: **[!UICONTROL Unitary event]** o **[!UICONTROL Segment qualification]**. È inoltre possibile scegliere di visualizzare solo i percorsi che utilizzano un evento, un gruppo di campi o un’azione particolare (**[!UICONTROL Activity filters]** e **[!UICONTROL Data filters]**). **[!UICONTROL Publication filters]** ti consente di selezionare una data di pubblicazione o un utente. Ad esempio, puoi scegliere di visualizzare solo le versioni più recenti dei percorsi live pubblicate ieri. Consulta [questa pagina](../building-journeys/using-the-journey-designer.md).

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

Se durante la configurazione degli schemi vengono forniti descrittori come &quot;xdm:alternateDisplayInfo&quot;, i nomi descrittivi sostituiranno i nomi visualizzati. Questa funzione risulta particolarmente utile quando si lavora con &quot;eVar&quot; e campi generici. È possibile configurare i descrittori di nomi descrittivi tramite una chiamata API. Per ulteriori informazioni, consulta la [Guida per gli sviluppatori del registro dello schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=it).

![](../assets/xdm-from-descriptors.png)

Se è disponibile un nome descrittivo, il campo verrà visualizzato come `<friendly-name>(<name>)`. Se non è disponibile alcun nome descrittivo, verrà mostrato il nome visualizzato, ad esempio `<display-name>(<name>)`. Se non è definito nessuno dei due, verrà visualizzato solo il nome tecnico del campo `<name>`.

>[!NOTE]
>
>I nomi descrittivi non vengono recuperati quando si selezionano i campi da un’unione di schemi.

## Accessibilità{#accessibility}

Le funzioni di accessibilità di Adobe Journey Optimizer sono fornite da Adobe Experience Platform:

* Accessibilità da tastiera
* Contrasto colore
* Convalida dei campi obbligatori

[Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/accessibility/features.html){target=&quot;_blank&quot;} nella documentazione di Adobe Experience Platform.

In Adobe Journey Optimizer è possibile utilizzare le seguenti scelte rapide da tastiera più comuni:

| Azione | Tasti di scelta rapida |
| --- | --- |
| Spostarsi tra elementi, sezioni e gruppi di menu dell’interfaccia utente | Scheda |
| Consente di spostarsi all’indietro tra gli elementi, le sezioni e i gruppi di menu dell’interfaccia utente. | Maiusc+Tab |
| Sposta all’interno delle sezioni per impostare lo stato attivo su singoli elementi | Freccia |
| Seleziona o cancella un elemento attivo | Inserisci o Barra spaziatrice |
| Annullare una selezione, comprimere un pannello o chiudere una finestra di dialogo | Esc |

[Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/accessibility/custom.html){target=&quot;_blank&quot;} nella documentazione di Adobe Experience Platform.

È possibile utilizzare queste scelte rapide in parti specifiche di Journey Optimizer:

<table>
  <thead>
    <tr>
      <th>Elemento di interfaccia</th>
      <th>Azione</th>
      <th>Tasti di scelta rapida</th>
    </tr>
  </thead>
  <tr>
    <td>Elenco di percorsi, azioni, origini dati o eventi</td>
    <td>Creare un percorso, un’azione, un’origine dati o un evento</td>
    <td>C</td>
  </tr>
  <tr>
    <td rowspan="3">Area di lavoro di percorso in stato bozza</td>
    <td>Aggiungi un’attività dalla palette a sinistra nella prima posizione disponibile, dall’alto verso il basso</td>
    <td>Fai doppio clic sull’attività</td>
  </tr>
  <tr>
    <td>Seleziona tutte le attività</td>
    <td>Ctrl + A (Windows)<br/>Comando + A (Mac)</td>
  </tr>
  <tr>
    <td>Elimina le attività selezionate</td>
    <td>Elimina o Backspace, quindi Inserisci per confermare l’eliminazione</td>
  </tr>
  <tr>
  <td rowspan="3">

Riquadro di configurazione dei seguenti elementi:

<ul>
  <li>Attività in un percorso</li>
  <li>Evento</li>
  <li>Origine dati</li>
  <li>Azione</li>
</ul>

</td>
    <td>Passa al campo successivo da configurare</td>
    <td>Scheda</td>
  </tr>
  <tr>
    <td>Salva le modifiche e chiudi il riquadro di configurazione</td>
    <td>Invio</td>
  </tr>
  <tr>
    <td>Ignora le modifiche e chiudi il riquadro di configurazione</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td rowspan="4">Percorso in modalità di prova</td>
    <td>Attivare o disattivare la modalità di test</td>
    <td>T</td>
  </tr>
  <tr>
    <td>Attiva un evento in un percorso basato su eventi</td>
    <td>E</td>
  </tr>
  <tr>
    <td>

Attiva un evento in un percorso basato su segmenti per il quale l&#39;opzione **[!UICONTROL Single profile at a time]** è attivata

</td>
    <td>P</td>
  </tr>
  <tr>
    <td>Visualizza i registri di test</td>
    <td>L</td>
  </tr>
<!-- //Ajouter ce raccourci quand il marchera (actuellement, le raccourci Ctrl/Cmd+F du navigateur a priorité sur celui de AJO).//
  <tr>
    <td>Page with a search bar</td>
    <td>Select the search bar</td>
    <td>Ctrl/Command + F</td>
  </tr>
-->
  <tr>
    <td>Campo di testo</td>
    <td>Seleziona tutto il testo nel campo selezionato</td>
    <td>Ctrl + A (Windows)<br/>Comando + A (Mac)</td>
  </tr>
  <tr>
    <td rowspan="2">Finestra a comparsa</td>
    <td>Salva le modifiche o conferma l’azione</td>
    <td>Invio</td>
  </tr>
  <tr>
    <td>Chiudi la finestra</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td>Editor di espressioni semplici</td>
    <td>Selezionare e aggiungere un campo</td>
    <td>Fare doppio clic su un campo</td>
  </tr>
  <tr>
    <td>Esplorazione dei campi XDM</td>
    <td>Seleziona tutti i campi di un nodo</td>
    <td>Selezionare il nodo principale</td>
  </tr>
  <tr>
    <td>Anteprima payload</td>
    <td>Selezionare il payload</td>
    <td>Ctrl + A (Windows)<br/>Comando + A (Mac)</td>
  </tr>
</table>
