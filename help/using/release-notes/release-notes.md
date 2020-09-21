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
translation-type: ht
source-git-commit: 619f05137bfad573a5de23ceda5448180dad2d6a
workflow-type: ht
source-wordcount: '1527'
ht-degree: 100%

---


# Note sulla versione {#release-notes}

Questa pagina elenca tutte le nuove funzionalità e i miglioramenti introdotti per Journey Orchestration.
Puoi anche consultare la sezione [Aggiornamenti alla documentazione](../release-notes/documentation-updates.md).

## Versione di agosto 2020 {#august-release}

### Aggiornamenti per la disponibilità generale{#august-ga-update}

Il payload degli eventi di qualificazione dei segmenti ora contiene le seguenti informazioni contestuali, che è possibile utilizzare in condizioni e azioni: il comportamento (entrata, uscita), il timestamp della qualificazione e l’ID del segmento. [Leggi tutto](../building-journeys/segment-qualification-events.md)

### Aggiornamenti Alpha{#august-alpha-update}

Per scoprire l’ambito del programma Alpha, fai riferimento a questa [sezione](../alpha/alpha-overview.md).

<table>
<thead>
<tr>
<th><strong>Attività attivazione segmento</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Sono stati apportati i seguenti miglioramenti all’attività attivazione segmento:
</p>
<ul>
<li><p>Il nome dell’attività è stato modificato in “Leggi segmento”. </p>
</li>
<li><p>La configurazione dell’utilità di pianificazione del percorso è stata rimossa dalle proprietà dell’attività. Ora è accessibile direttamente dalle proprietà del percorso, in una sezione dedicata che verrà visualizzata se un’attività Leggi segmento è stata rilasciata nell’area di lavoro. </p>
</li>
<li><p>Ora puoi testare il percorso su un profilo unitario e monitorare l’avanzamento del profilo nel percorso utilizzando il flusso visivo.</p>
</li>
</ul>
<p>Per ulteriori informazioni, consulta la <a href="../alpha/alpha-segment-trigger.md">documentazione dettagliata</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Eventi basati su regole</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Sono stati apportati i seguenti miglioramenti agli eventi basati su regole:
</p>
<ul>
<li><p>Ora puoi sfruttare tutti i dati dell’evento comportamentale di Adobe Analytics che già acquisisci e trasferisci in Platform per attivare i percorsi e automatizzare le esperienze per i clienti. <a href="../alpha/alpha-events.md#analytics-data">Leggi tutto</a></p>
</li>
<li><p>Ora, quando attivi un evento basato su regole in modalità di test, puoi visualizzare direttamente la condizione dell’ID evento. Inoltre, è stata aggiunta una descrizione del comando accanto a ciascun campo che fa parte della valutazione delle regole. <a href="../alpha/alpha-events.md#configuring-rule-based">Leggi tutto</a></p>
</li>
<li><p>La schermata di definizione degli eventi basati su regole è stata riorganizzata per migliorare l’esperienza. <a href="../alpha/alpha-events.md#test-rule-based">Leggi tutto</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Rilascio Alpha - Luglio 2020 {#alpha-release---july-2020}

Il programma Alpha offre funzioni che sono attualmente in fase di test per un numero limitato di clienti. Questo ci permette di migliorare il nostro prodotto in base al feedback ricevuto. Le funzioni non sono disponibili per tutti i clienti di Journey Orchestration.

Queste funzioni sono descritte in una [sezione](../alpha/alpha-overview.md) dedicata.

<table>
<thead>
<tr>
<th><strong>Interfaccia utente migliorata</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>La navigazione all’interno dei menu di Journey Orchestration è stata migliorata per fornire un’interfaccia coerente con Adobe Experience Platform:
</p>
<ul>
<li><p>I menu sono stati spostati dalla parte superiore al lato sinistro dell’interfaccia. </p>
</li>
<li><p>Le funzionalità di amministrazione sono state raggruppate in un’unica dashboard.</p>
</li>
</ul>
<p>Per ulteriori informazioni, consulta la <a href="../alpha/alpha-interface.md">documentazione dettagliata</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Attività attivazione segmento</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>L’attività attivazione segmento consente di fare in modo che tutti i singoli utenti appartenenti a un segmento Adobe Experience Platform entrino in un percorso. L’entrata in un percorso può essere eseguita una volta o su base regolare. <a href="../alpha/alpha-segment-trigger.md">Leggi tutto</a>
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Eventi basati su regole</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Abbiamo semplificato la configurazione degli eventi di esperienza. Stiamo introducendo un nuovo metodo che non richiede l’uso di un ID evento. Ora quando configuri l’evento in Journey Orchestration puoi definire un evento basato su regole. <a href="../alpha/alpha-events.md">Leggi tutto</a>
</p>
</td>
</tr>
</tbody>
</table>


## Versione secondo trimestre - giugno 2020 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Miglioramenti dell’integrazione di Adobe Experience Platform</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Sono stati apportati i seguenti miglioramenti all’integrazione di Adobe Experience Platform:</p>
<ul>
<li><p>Una nuova attività consente di ascoltare le entrate/uscite dei segmenti Adobe Experience Platform per consentire alle persone di accedere a un percorso o proseguire in esso. <a href="../building-journeys/segment-qualification-events.md">Leggi tutto</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Grazie alla nuova scheda <strong>Segments</strong> è ora possibile creare e modificare i segmenti di Adobe Experience Platform senza uscire dall’interfaccia di Journey Orchestration.<a href="../segment/about-segments.md">Leggi tutto</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>Nell’editor delle espressioni semplici, i segmenti di Adobe Experience Platform ora sono elencati direttamente nella struttura di navigazione per consentire una configurazione semplice di condizioni come “questa persona appartiene al segmento A?”.<a href="../segment/using-a-segment.md">Leggi tutto</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Ora Journey Orchestration passa automaticamente ad Adobe Experience Platform i passaggi eseguiti nei percorsi. Ciò include i potenziali errori rilevati. Queste informazioni possono essere utilizzate per ottenere rapporti e ai fini di risoluzione dei problemi attraverso l’esecuzione di query sugli eventi del passaggio del percorso o per tutti i percorsi. <a href="../building-journeys/sharing-overview.md">Leggi tutto</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>Ora Journey Orchestration può essere collegata alle sandbox Adobe Experience Platform, sia di produzione che non di produzione. Le sandbox sono una funzione beta. <a href="../about/access-management.md#sandboxes">Leggi tutto</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Miglioramenti di designer del percorso e modalità di test</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Sono stati apportati i seguenti miglioramenti al designer del percorso e alla modalità di test:</p>
<ul>
<li><p>È ora possibile copiare e incollare le attività da un percorso all’altro, selezionando 1 o N attività di percorso. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">Leggi tutto</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>Dopo aver attivato un evento per la creazione di un profilo di test per l’accesso a un percorso, ora potrai vederne i progressi grazie a un flusso visivo colorato. In caso di errore nel percorso, vengono visualizzati anche i dettagli degli errori. <a href="../building-journeys/testing-the-journey.md#firing_events">Leggi tutto</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>Lo stato di percorso <strong>Finished</strong> è stato rinominato <strong>Closed (no entrance)</strong> per riflettere meglio il suo significato.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Altri miglioramenti**

Per evitare di inviare un numero eccessivo di chiamate API a sistemi di terze parti, stiamo introducendo una nuova API pubblica per impostare le regole di “limitazione di utilizzo”. Le regole di limitazione di utilizzo consentono di definire un numero massimo di chiamate a un endpoint API per millisecondi. [Leggi tutto](../api/capping.md)

Adesso il controllo di accesso consente una maggiore granularità nella gestione degli accessi utente. Disponibilità effettiva: 30 giugno 2020. [Leggi tutto](../about/access-management.md#create-product-profile)

Journey Orchestration è ora disponibile in APAC (datacenter australiano). Disponibilità effettiva: 30 giugno 2020

L’interfaccia Journey Orchestration è disponibile in giapponese.

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
<li>La casella di controllo <strong>Profile Timezone (Fuso orario profilo)</strong> consente di usare il fuso orario del profilo di Adobe Experience Platform della persona che accede al percorso, se disponibile. In caso contrario, viene utilizzato il fuso orario specificato nell’elenco a discesa. Questa funzione non è compatibile con i percorsi che utilizzano eventi privi di spazio dei nomi.</li>
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

* Dopo l’introduzione negli Stati Uniti, ora Journey Orchestration è accessibile nell’**EMEA**. L’applicazione e la documentazione sono disponibili in francese e tedesco.

* Experience League è ora integrato all’interno del prodotto, il che semplifica l’accesso ai contenuti correlati, consentendoti di trarre il massimo da Experience Cloud. L’accesso diretto alla documentazione di Journey Orchestration è disponibile nella parte inferiore della scheda dell’aiuto. Inoltre, puoi fare clic su Aiuto > Feedback per segnalare i problemi o condividere le idee con Adobe.

* La scelta rapida da tastiera **C**, che consente di creare un nuovo elemento è ora disponibile in tutte le schermate elenco: percorsi, origini dati, azioni ed eventi. [Ulteriori informazioni](../about/user-interface.md#section_ksq_zr1_ffb)

* Ora è possibile **eliminare** i percorsi interrotti. I rapporti associati a questi percorsi eliminati non saranno disponibili.

* Durante l’esplorazione dei **campi di Adobe Experience Platform** (formato XDM), ora viene mostrato il nome visualizzato in aggiunta al nome del campo. Queste informazioni vengono recuperate dalla definizione dello schema di Experience Data Model. Il nome visualizzato alternativo viene mostrato, se disponibile. Questa descrizione semplice e intuitiva, particolarmente utile per i campi eVar, ti consente di identificare più facilmente i campi. [Ulteriori informazioni](../about/user-interface.md#friendly-names-display)

## Versione GA - dicembre 2019 {#ga-release---december-2019}

Journey Orchestration adesso è GA.

Crea casi di utilizzo di orchestrazione in tempo reale sulla base dei dati contestuali memorizzati negli eventi o nelle origini dati.

Journey Orchestration consente l’orchestrazione in tempo reale basata su dati contestuali derivati dagli eventi, su informazioni provenienti da Adobe Experience Platform oppure su dati di servizi API di terze parti. Nell’ambito di flussi di più passaggi denominati percorsi, l’applicazione determina le migliori azioni da eseguire in futuro che sono specifiche del consumatore, in base al profilo e ai comportamenti adottati. Tale procedura include sia la tempistica ottimale, sia il tipo di azione, ad esempio la notifica di un sistema di terze parti o l’invio al consumatore di una notifica push tramite le funzionalità di messaggistica transazionali di Adobe Campaign Standard (richiesto). Queste decisioni sono prese sulla base di regole e punteggi Sensei.

[](../action/working-with-adobe-campaign.md)Ulteriori informazioni su Journey Orchestration.

Risorse aggiuntive:

* [Esercitazioni](https://docs.adobe.com/content/help/it-IT/journey-orchestration-learn/tutorials/understanding-journey-orchestration.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)
