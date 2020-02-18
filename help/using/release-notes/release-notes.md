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
source-git-commit: 8023d7780d43f1de4447c63568f641ce204722c7

---


# Note sulla versione {#release-notes}

Questa pagina elenca tutte le nuove funzioni e i miglioramenti per l&#39;orchestrazione del viaggio.
È inoltre possibile consultare la [documentazione Aggiornamenti](../release-notes/documentation-updates.md).

## Rilascio Q1 - febbraio 2019 {#q1-release---february-2019}

**Gestione del fuso orario**

I timezoni vengono ora gestiti a livello di viaggio. Nelle proprietà di viaggio sono stati aggiunti due parametri:

* L’elenco a discesa **Fuso orario** consente di selezionare un fuso orario specifico. Per impostazione predefinita, viene utilizzato il fuso orario del browser.

* La casella **Fuso orario** profilo consente di utilizzare il fuso orario del profilo della piattaforma esperienza della persona che accede al viaggio, se disponibile. In caso contrario, verrà utilizzato il fuso orario definito nel menu a discesa. Questa funzione non è compatibile con viaggi senza spazio dei nomi.

**Aiuto contestuale**

È ora disponibile una funzione di aiuto contestuale nelle diverse schermate di orchestrazione del viaggio. Ciò significa che, con un solo clic, è possibile accedere direttamente alla documentazione sulla funzionalità attualmente in uso.

Per visualizzare la guida contestuale, fai clic sull’icona &quot;i&quot; nell’angolo superiore destro dello schermo.

Al momento, questa funzione è disponibile nelle schermate Home, Origini dati, Eventi e Azioni.

**Altre modifiche**

* In modalità di prova, un nuovo parametro consente di definire il periodo di tempo.  le attività di attesa ora possono durare. Questo consente di accedere rapidamente ai risultati del test.

* In modalità di prova, ora puoi attivare tutti gli eventi del viaggio.


* un nuovo parametro consente di definire il periodo di tempo più lungo.  le attività di attesa ora possono durare. Questo consente di accedere rapidamente ai risultati del test.

* L&#39;orchestrazione dei percorsi è ora disponibile nell&#39;area EMEA.

* Nuova icona nella palette per visualizzare o meno gli elementi non disponibili. sans namespace. par default .

* canvas, scollegamento, minuto, qui dit nodo scollegato.

* taglio corto C titoli les listes

* interfaccia utente della palette, risultati di ricerca al icone

* Il capper del pouvoir les definisce un&#39;area esterna dell&#39;API (origini dati o azioni). marque n&#39;accettte que 500 chiamate par postde, le pourra mettre un limite di 500 chiamate secondi qui evite de surcharger system de loyalty tiers

* log du test log. Avant status = error. quand sui sistemi di appello. Possibilityé de voir codice erreur frase qu&#39;à renvoyé le systeme. -> ds un test en cas d&#39;erreur, livelli di sistema, codice di errore, risposta di errore.

* Interrompi viaggio

* percorso: versione 1 il incontrato è più recente

1er marte.


## Rilascio GA - Dicembre 2019 {#ga-release---december-2019}

L&#39;orchestrazione del viaggio ora è GA.

Creare casi di utilizzo di orchestrazione in tempo reale utilizzando i dati contestuali memorizzati in eventi o origini dati.

L&#39;orchestrazione del percorso consente l&#39;orchestrazione in tempo reale basata su dati contestuali derivati da eventi, informazioni provenienti da Adobe Experience Platform o dati provenienti da servizi API di terze parti. L&#39;applicazione determina nei flussi in più passaggi denominati viaggi le azioni migliori successive specifiche per il consumatore, in base al suo profilo e ai suoi comportamenti. Questo include sia la tempistica ottimale, sia il tipo di azione, ad esempio l&#39;invio al consumatore di una notifica push tramite le funzionalità di messaggistica transazionali di Adobe Campaign Standard (richiede Adobe Campaign Standard) o la notifica di un sistema di terze parti. Queste decisioni si basano su regole e voti Sensei.

[Ulteriori](../action/working-with-adobe-campaign.md) informazioni sull&#39;orchestrazione del viaggio.

Risorse aggiuntive:

* [Esercitazioni](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)