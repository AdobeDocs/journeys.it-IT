---
title: Note sulla versione
description: Informazioni sulle note sulla versione
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
source-git-commit: 73f1a503ea2c8b3494460c666a05078ed914e58b

---


# Note sulla versione {#release-notes}

Questa pagina elenca tutte le nuove funzioni e i miglioramenti per l&#39;orchestrazione del viaggio.
È inoltre possibile consultare la [documentazione Aggiornamenti](../release-notes/documentation-updates.md).

## Rilascio Q1 - Marzo 2020 {#q1-release---march-2020}

**Cosa c&#39;è di nuovo?**

<table>
<thead>
<tr>
<th><strong>Miglioramenti della modalità di test</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Sono stati apportati i seguenti miglioramenti alla modalità di prova:</p>
<ul>
<li>Quando un viaggio utilizza diversi eventi, ora puoi attivarli singolarmente da un elenco a discesa, nella schermata di configurazione <strong>dell'</strong> evento della modalità di prova. <a href="../building-journeys/testing-the-journey.md#firing_events">Leggi tutto</a></p></li>
<li><p>Quando una o più attività <strong>Aspetta</strong> vengono utilizzate in un viaggio, ora puoi definire l'ora in cui ciascuna di queste attività durerà in modalità di prova. Il tempo predefinito è 10 secondi. Potete modificare questo valore usando il parametro Tempo di <strong>attesa nel test</strong> , nell’angolo in basso a sinistra. <a href="../building-journeys/testing-the-journey.md">Leggi tutto</a></p><img src="../assets/rn-test.png"/>
</li>
<li>Nei registri <strong>di</strong>test, in caso di errore durante la chiamata a un sistema di terze parti (origine dati o azione), ora vengono visualizzati il codice di errore e la risposta di errore. <a href="../building-journeys/testing-the-journey.md#viewing_logs">Leggi tutto</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Gestione centralizzata del fuso orario</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>La gestione del fuso orario è ora centralizzata nel pannello delle proprietà del viaggio. Nelle proprietà di viaggio sono stati aggiunti due parametri:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>L’elenco a discesa <strong>Fuso orario</strong> consente di selezionare un fuso orario specifico. Per impostazione predefinita, viene utilizzato il fuso orario del browser.</li>
<li>La casella <strong>Fuso orario</strong> profilo consente di utilizzare il fuso orario del profilo della piattaforma esperienza della persona che accede al viaggio, se disponibile. In caso contrario, viene utilizzato il fuso orario definito nell'elenco a discesa. Questa funzione non è compatibile con i viaggi che utilizzano eventi privi di spazio nomi.</li>
</ul>
<p>Per ulteriori informazioni, consultare le sezioni <a href="../building-journeys/changing-properties.md#timezone">Modifica delle proprietà</a> e Gestione <a href="../building-journeys/timezone-management.md">del</a> fuso orario.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Miglioramenti al designer del viaggio</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>La <strong>palette</strong>Viaggio, a sinistra del designer del viaggio, è stata migliorata:</p>
<ul>
<li>Una nuova icona, accanto alla barra **Search**, consente di nascondere o visualizzare gli elementi non disponibili nella palette, ad esempio gli eventi che utilizzano uno spazio nomi diverso da quelli utilizzati nel percorso. Per impostazione predefinita, gli elementi non disponibili sono nascosti.</li>
<li>Quando si utilizza il campo <strong>Cerca</strong> , ora viene visualizzato il numero di risultati per ogni categoria di attività canvas.</li>
<li>È stata migliorata la navigazione tra le diverse categorie di attività.</li>
</ul>
<p>Nella finestra di progettazione dei viaggi, ora puoi verificare di aver effettuato l’accesso all’ultima versione del viaggio. Queste informazioni vengono visualizzate accanto al numero di versione.</p>
<p>Nel <strong>quadro</strong>del viaggio, quando due attività vengono disconnesse, ora viene visualizzato un messaggio di avviso.</p>
<img src="../assets/rn-canvas.png"/>
<p>Per ulteriori informazioni, consulta la documentazione <a href="../building-journeys/using-the-journey-designer.md"></a>dettagliata.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Aiuto contestuale</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>È ora disponibile una guida contestuale nelle diverse schermate dell'elenco di orchestrazione del viaggio (viaggi, eventi, azioni e origini dati). Questo consente di visualizzare una descrizione rapida delle funzionalità correnti e di accedere agli articoli e ai video correlati.</p>
<p>Per visualizzare la guida contestuale, fate clic sull’ <img src="../assets/icon-context.png"/> icona nell’angolo in alto a destra dello schermo. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Altri miglioramenti**

* Oltre agli Stati Uniti, ora è disponibile l&#39;orchestrazione dei viaggi nell&#39; **area EMEA**. La domanda e la documentazione sono disponibili in francese e tedesco.

* Experience League è ora integrato nel prodotto. Questo semplifica l&#39;accesso ai contenuti correlati e consente di trarre il massimo da Experience Cloud. L&#39;accesso diretto alla documentazione sull&#39;orchestrazione del percorso è disponibile nella parte inferiore della scheda Aiuto. Inoltre, fate clic su Aiuto > Feedback per segnalare i problemi o condividere le idee con Adobe.

* La scelta rapida da tastiera **C** , che consente di creare un nuovo elemento, è ora disponibile in tutte le schermate elenco: viaggi, origini dati, azioni ed eventi. [Leggi tutto](../about/user-interface.md#section_ksq_zr1_ffb)

* Ora è possibile **eliminare** i viaggi interrotti. I rapporti associati a questi viaggi eliminati non saranno disponibili.

* Quando si esplorano i campi **della piattaforma** dati (formato XDM), ora viene visualizzato il nome visualizzato oltre al nome del campo. Queste informazioni vengono recuperate dalla definizione dello schema nel modello dati esperienza. Quando disponibile, viene visualizzato il nome visualizzato alternativo. Questa descrizione semplice e intuitiva, particolarmente utile per i campi eVar, consente di identificare più facilmente i campi. [Leggi tutto](../about/user-interface.md#friendly-names-display)

## Rilascio GA - Dicembre 2019 {#ga-release---december-2019}

L&#39;orchestrazione del viaggio ora è GA.

Creare casi di utilizzo di orchestrazione in tempo reale utilizzando i dati contestuali memorizzati in eventi o origini dati.

L&#39;orchestrazione del percorso consente l&#39;orchestrazione in tempo reale basata su dati contestuali derivati da eventi, informazioni provenienti da Adobe Experience Platform o dati provenienti da servizi API di terze parti. L&#39;applicazione determina nei flussi in più passaggi denominati viaggi le azioni migliori successive specifiche per il consumatore, in base al suo profilo e ai suoi comportamenti. Questo include sia la tempistica ottimale, sia il tipo di azione, ad esempio l&#39;invio al consumatore di una notifica push tramite le funzionalità di messaggistica transazionali di Adobe Campaign Standard (richiede Adobe Campaign Standard) o la notifica di un sistema di terze parti. Queste decisioni si basano su regole e voti Sensei.

[Ulteriori](../action/working-with-adobe-campaign.md) informazioni sull&#39;orchestrazione del viaggio.

Risorse aggiuntive:

* [Esercitazioni](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)