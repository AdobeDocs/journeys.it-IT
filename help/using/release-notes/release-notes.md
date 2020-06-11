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
source-git-commit: 556dbe88d2717a387e5f0ce8795c9fa02a45ac6f
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 70%

---


# Note sulla versione {#release-notes}

Questa pagina elenca tutte le nuove funzionalità e i miglioramenti introdotti per Journey Orchestration.
Puoi anche consultare la sezione [Aggiornamenti alla documentazione](../release-notes/documentation-updates.md).

## Release Q2 - Giugno 2020 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Miglioramenti all'integrazione con Adobe Experience Platform</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Sono stati apportati i seguenti miglioramenti all'integrazione con la piattaforma:</p>
<ul>
<li><p>Una nuova attività consente di ascoltare entrate/uscite del segmento Piattaforma per far entrare o andare avanti le persone in un viaggio. <a href="../building-journeys/event-activities.md#segment-qualification">Leggi tutto</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>È ora possibile creare e modificare i segmenti della piattaforma senza uscire dall'interfaccia di orchestrazione del percorso, grazie a una nuova scheda <strong>Segmenti</strong> .<a href="../segment/about-segments.md">Leggi tutto</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>Nell'editor delle espressioni semplici, i segmenti della piattaforma ora sono elencati direttamente nella struttura di navigazione per consentire una facile configurazione di condizioni come "questa persona appartiene al segmento A?".<a href="../segment/using-a-segment.md">Leggi tutto</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>L'orchestrazione del percorso ora passa automaticamente, ad Adobe Data Platform, i passaggi eseguiti nei viaggi. Ciò include potenziali errori rilevati. Queste informazioni possono essere utilizzate per ottenere rapporti e risoluzione dei problemi eseguendo query sugli eventi del Passaggio del viaggio per un viaggio particolare o per tutti i viaggi. <a href="../building-journeys/sharing-overview.md">Leggi tutto</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
</li>
<li><p>È ora possibile collegare l'orchestrazione del percorso alle sandbox della piattaforma di produzione e non di produzione. Le sandbox sono una funzione beta. Disponibilità effettiva: 30 giugno 2020. <a href="../about/access-management.md#sandboxes">Leggi tutto</a></p>
</li>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Miglioramenti di Progettazione viaggi e modalità di prova</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Sono stati apportati i seguenti miglioramenti al progettista del viaggio e alla modalità di prova:</p>
<ul>
<li><p>È ora possibile copiare le attività Incolla da un viaggio all'altro, selezionando 1 o N attività di viaggio. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">Leggi tutto</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>Dopo aver attivato un evento per creare un profilo di test per entrare in un viaggio, potete ora vedere i suoi progressi lungo il percorso grazie a un flusso visivo colorato. In caso di errore nel percorso, vengono visualizzati anche i dettagli degli errori. <a href="../building-journeys/testing-the-journey.md#firing_events">Leggi tutto</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>Lo stato di <strong>viaggio Finito</strong> è stato rinominato <strong>Chiuso (senza entrata)</strong> per riflettere meglio cosa significa questo stato.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Altri miglioramenti**

Per evitare di inviare troppe chiamate API a sistemi di terze parti, stiamo introducendo una nuova API pubblica per impostare le regole di &quot;capping&quot;. Le regole di intercettazione consentono di definire un numero massimo di chiamate a un endpoint API per millisecondi. [Leggi tutto](../api/capping.md)

Il controllo degli accessi ora consente una maggiore granularità nella gestione degli accessi utente. Disponibilità effettiva: 30 giugno 2020. [Leggi tutto](../about/access-management.md#create-product-profile)

È ora disponibile l&#39;Orchestrazione del viaggio in APAC (datacenter australiano). Disponibilità effettiva: 30 giugno 2020

L&#39;interfaccia di orchestrazione del viaggio è disponibile in giapponese.

## Versione primo trimestre - marzo 2020 {#q1-release---march-2020}

**Novità?**

<table>
<thead>
<tr>
<th><strong>Miglioramenti della modalità di test</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Sono stati apportati i seguenti miglioramenti alla modalità di test:</p>
<ul>
<li>Quando un percorso utilizza diversi eventi, adesso puoi attivarli singolarmente da un elenco a discesa, dalla schermata <strong>Event configuration (Configurazione dell’evento)</strong> della modalità di test. <a href="../building-journeys/testing-the-journey.md#firing_events">Ulteriori informazioni</a></p></li>
<li><p>Quando una o più attività <strong>Attendi</strong> vengono utilizzate in un percorso, ora puoi impostare la durata di ciascuna in modalità di test. Il tempo predefinito è di 10 secondi. Puoi modificare questo valore usando il parametro <strong>Wait time in test (Tempo di attesa nel test)</strong>, nell’angolo in basso a sinistra. <a href="../building-journeys/testing-the-journey.md">Ulteriori informazioni</a></p><img src="../assets/rn-test.png"/>
</li>
<li>Nei <strong>registri di test</strong>, in caso di errore durante la chiamata a un sistema di terze parti, che sia origine dati o azione, adesso vengono visualizzati il codice di errore e la risposta relativa. <a href="../building-journeys/testing-the-journey.md#viewing_logs">Ulteriori informazioni</a>
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
<p>La gestione del fuso orario è ora centralizzata nel pannello delle proprietà del percorso. Nelle proprietà del percorso sono stati aggiunti due parametri:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>L’elenco a discesa <strong>Timezone (Fuso orario)</strong> consente di selezionare un fuso orario specifico. Per impostazione predefinita, viene utilizzato il fuso orario del browser. </li>
<li>La casella di controllo <strong>Profile Timezone (Fuso orario profilo)</strong> consente di usare il fuso orario del profilo di Experience Platform della persona che accede al percorso, se disponibile. In caso contrario, viene utilizzato il fuso orario specificato nell’elenco a discesa. Questa funzione non è compatibile con i percorsi che utilizzano eventi privi di spazio dei nomi.</li>
</ul>
<p>Per ulteriori informazioni, consulta le sezioni <a href="../building-journeys/changing-properties.md#timezone">Modifica delle proprietà</a> e <a href="../building-journeys/timezone-management.md">Gestione del fuso orario</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Miglioramenti al designer del percorso</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>È stata migliorata la <strong>palette</strong> del percorso, posizionata a sinistra rispetto al designer del percorso:</p>
<ul>
<li>Una nuova icona, posta accanto alla barra di <strong>ricerca</strong>, consente di nascondere o visualizzare gli elementi non disponibili nella palette, ad esempio quelli che utilizzano uno spazio dei nomi diverso rispetto a quelli usati nel percorso. Per impostazione predefinita, gli elementi non disponibili sono nascosti.</li>
<li>Quando si utilizza il campo <strong>ricerca</strong>, ora viene visualizzato il numero di risultati per ogni categoria di attività dell’area di lavoro.</li>
<li>È stata migliorata la navigazione tra le diverse categorie di attività.</li>
</ul>
<p>Nel designer del percorso, ora puoi verificare di aver effettuato l’accesso all’ultima versione del percorso. Queste informazioni vengono visualizzate accanto al numero di versione.</p>
<p>Quando due attività vengono disconnesse, adesso nell’<strong>area di lavoro</strong> del percorso viene visualizzato un messaggio di avviso.</p>
<img src="../assets/rn-canvas.png"/>
<p>Per ulteriori informazioni, consulta la <a href="../building-journeys/using-the-journey-designer.md">documentazione dettagliata</a>.</p>
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
<p>È ora disponibile un aiuto contestuale nelle diverse schermate dell’elenco di Journey Orchestration (percorsi, eventi, azioni e origini dati). In tal modo, puoi visualizzare una descrizione rapida delle funzionalità correnti e accedere agli articoli e ai video correlati.</p>
<p>Per visualizzare l’aiuto contestuale, fai clic sull’icona <img src="../assets/icon-context.png"/> posta nell’angolo in alto a destra dello schermo. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Altri miglioramenti**

* Dopo l’introduzione negli Stati Uniti, adesso Journey Orchestration è accessibile nell’**EMEA**. L’applicazione e la documentazione sono disponibili in francese e tedesco.

* Experience League è ora integrato all’interno del prodotto, il che semplifica l’accesso ai contenuti correlati, consentendoti di trarre il massimo da Experience Cloud. L’accesso diretto alla documentazione di Journey Orchestration è disponibile nella parte inferiore della scheda dell’aiuto. Inoltre, puoi fare clic su Aiuto > Feedback per segnalare i problemi o condividere le idee con Adobe.

* La scelta rapida da tastiera **C**, che consente di creare un nuovo elemento è ora disponibile in tutte le schermate elenco: percorsi, origini dati, azioni ed eventi. [Ulteriori informazioni](../about/user-interface.md#section_ksq_zr1_ffb)

* Ora è possibile **eliminare** i percorsi interrotti. I rapporti associati a questi percorsi eliminati non saranno disponibili.

* Durante l’esplorazione dei campi di **Data Platform** (formato XDM), ora viene mostrato il nome visualizzato, in aggiunta al nome del campo. Queste informazioni vengono recuperate dalla definizione dello schema di Experience Data Model. Il nome visualizzato alternativo viene mostrato, se disponibile. Questa descrizione semplice e intuitiva, particolarmente utile per i campi eVar, ti consente di identificare più facilmente i campi. [Ulteriori informazioni](../about/user-interface.md#friendly-names-display)

## Versione GA - dicembre 2019 {#ga-release---december-2019}

Journey Orchestration adesso è GA.

Crea casi di utilizzo di orchestrazione in tempo reale sulla base dei dati contestuali memorizzati negli eventi o nelle origini dati.

Journey Orchestration consente l’orchestrazione in tempo reale basata su dati contestuali derivati dagli eventi, su informazioni provenienti da Adobe Experience Platform oppure su dati di servizi API di terze parti. Nell’ambito di flussi di più passaggi denominati percorsi, l’applicazione determina le migliori azioni da eseguire in futuro che sono specifiche del consumatore, in base al profilo e ai comportamenti adottati. Tale procedura include sia la tempistica ottimale, sia il tipo di azione, ad esempio la notifica di un sistema di terze parti o l’invio al consumatore di una notifica push tramite le funzionalità di messaggistica transazionali di Adobe Campaign Standard (richiesto). Queste decisioni sono prese sulla base di regole e punteggi Sensei.

[](../action/working-with-adobe-campaign.md)Ulteriori informazioni su Journey Orchestration.

Risorse aggiuntive:

* [Esercitazioni](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)
