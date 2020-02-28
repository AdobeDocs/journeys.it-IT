---
title: Risoluzione dei problemi
description: Ulteriori informazioni sulla risoluzione dei problemi
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 25715e66b5495347e0c5ee2b1d75d44aa9cd3125

---


# Risoluzione dei problemi{#concept_nlv_bcv_2fb}

In questa sezione viene descritto come risolvere i problemi dei viaggi prima di eseguire test o pubblicare. Tutti i controlli elencati di seguito possono essere eseguiti quando il viaggio è in modalità di prova o quando il viaggio è in diretta. Si consiglia di eseguire tutti i controlli riportati di seguito in modalità di prova, quindi di procedere alla pubblicazione. Vedere [](../building-journeys/testing-the-journey.md).

## Verifica degli errori prima del test{#section_h3q_kqk_fhb}

Prima di testare e pubblicare il percorso, verifica che tutte le attività siano configurate correttamente. Non è possibile eseguire test o pubblicazioni se il sistema rileva ancora degli errori.

Gli errori vengono visualizzati con un simbolo di avviso visualizzato sulle attività stesse sul quadro. Posizionare il cursore sul punto esclamativo per visualizzare il messaggio di errore. Se fate clic sull&#39;attività, la riga dovrebbe essere visualizzata in errore con un avviso. Ad esempio, se un campo obbligatorio è vuoto, viene visualizzato un errore.

![](../assets/journey63.png)

Ad esempio, nel quadro, quando due attività sono disconnesse, viene visualizzato un avviso.

![](../assets/canvas-disconnected.png)

Accanto all&#39; **[!UICONTROL Test]** interruttore e al **[!UICONTROL Publish]** pulsante, è possibile visualizzare un segnale di avviso. Questo segnale di avviso visualizza gli errori rilevati dal sistema e impedisce l&#39;attivazione della modalità di prova o la pubblicazione del percorso. Nella maggior parte dei casi, gli errori rilevati dal sistema sono collegati a errori visibili sulle attività, ma a volte sono collegati ad altri problemi. In questo caso, potete visualizzarli, cercare di identificare il problema utilizzando la descrizione dell&#39;errore. Se non riuscite a identificare il problema, potete copiare i dettagli e inviarli all’amministratore o al supporto tecnico. Gli errori che bloccano il test e gli errori che bloccano la pubblicazione sono simili.

Il sistema rileva due tipi di problemi: errori e avvisi Errori nella pubblicazione del blocco e nel test dell&#39;attivazione. Gli avvisi indicano potenziali problemi che non impediscono l&#39;attivazione o la pubblicazione del test. Vedrete una descrizione del problema e un ID registro dei problemi del tipo ERR_XXX_XXX. Questo aiuterà il supporto tecnico a identificare il problema.

Sul segno accanto all’ **[!UICONTROL Test]** interruttore e al **[!UICONTROL Publish]** pulsante possono essere visualizzati due colori diversi. Il segno viene visualizzato in rosso in caso di errori. Viene visualizzato in arancione in caso di avvisi.

![](../assets/journey75.png)

Gli errori e gli avvisi globali relativi al viaggio vengono visualizzati per primi nell&#39;elenco. Gli errori e gli avvisi relativi ad attività specifiche sono elencati dopo, per ordine di attività o per aspetto nel viaggio da sinistra a destra. Il **[!UICONTROL Copy details]** pulsante consente di copiare le informazioni tecniche sul percorso che il team di assistenza può utilizzare per risolvere i problemi.

## Controllo dell&#39;invio corretto degli eventi{#section_rqz_11t_dgb}

Il punto di partenza di un viaggio è sempre un evento. Potete eseguire i test utilizzando strumenti come Postman.

Potete verificare se la chiamata API inviata tramite questi strumenti viene inviata correttamente o meno. Se ricevi nuovamente un errore, significa che la chiamata ha un problema. Controllate di nuovo il payload, l&#39;intestazione (e in particolare l&#39;ID organizzazione) e l&#39;URL di destinazione. Potete chiedere all’amministratore qual è l’URL corretto da utilizzare.

Gli eventi non vengono inviati direttamente dall&#39;origine all&#39;orchestrazione del percorso. In effetti, l’orchestrazione del percorso si basa sulle API di caricamento in streaming della piattaforma Experience. Di conseguenza, in caso di problemi relativi agli eventi, potete fare riferimento a questa [pagina](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingestion_FAQ.md) per la risoluzione dei problemi delle API di assimilazione in streaming.

## Verifica se le persone entrano nel viaggio{#section_x4v_zzs_dgb}

L&#39;orchestrazione del viaggio misura le entrate delle persone in un viaggio in tempo reale.

Se l’invio dell’evento è stato completato con successo ma non viene visualizzato alcun ingresso nel viaggio, significa che qualcosa va storto tra l’invio dell’evento e la ricezione dell’evento nel viaggio.

Di seguito sono riportati alcuni elementi che l’amministratore deve controllare:

* Siete sicuri che il percorso in cui prevedete che l&#39;evento in arrivo sia in modalità di prova o live?
* Avete salvato l’evento prima di copiare il payload dall’anteprima del payload?
* Il payload dell&#39;evento contiene un ID evento?
* Hai raggiunto l&#39;URL giusto?
* Avete seguito la struttura del payload API di Streaming Ingestion utilizzando l&#39;anteprima della struttura del payload nel riquadro di configurazione dell&#39;evento? Vedere [](../event/previewing-the-payload.md).
* Avete usato le coppie chiave/valore corrette nell’intestazione dell’evento?

   ```
   X-gw-ims-org-id - your ORGID
   Content-type - application/json
   ```

## Controllo della modalità di navigazione delle persone nel percorso{#section_l5y_yzs_dgb}

L&#39;orchestrazione del viaggio misura il progresso degli individui all&#39;interno di un viaggio. È facile identificare dove e perché una persona è stata fermata.

Di seguito sono riportati alcuni elementi da verificare:

* È dovuto a una condizione che esclude la persona? Ad esempio, la condizione è &quot;genere = maschio&quot; e la persona è una donna. Questo controllo può essere eseguito da un utente aziendale se la condizione non è troppo complessa.
* È dovuto a una chiamata a un&#39;origine dati che non risponde? Quando il viaggio è in prova, queste informazioni possono essere visualizzate nei registri in modalità di prova. Quando il viaggio è live, un amministratore può testare le chiamate dirette all&#39;origine dati e verificare la risposta ricevuta. Un amministratore può anche duplicare il percorso e testarlo.

## Controllo dell&#39;invio dei messaggi{#section_qb1_yzs_dgb}

Se gli individui scorrono nel modo giusto durante il viaggio ma non ricevono i messaggi che dovrebbero ricevere, potete verificare se:

* Messaggi transazionali ha tenuto correttamente conto della richiesta di invio del messaggio. Un utente aziendale può accedere al messaggio di transazione che dovrebbe essere inviato e verificare se l&#39;ora dell&#39;esecuzione più recente corrisponde al tempo di esecuzione del viaggio. Può inoltre controllare le ultime chiamate/eventi API ricevuti dai messaggi transazionali.
* Messaggi transazionali inviati correttamente. Nei registri di invio del messaggio di transazione, puoi vedere lo stato di ogni esecuzione. Potete vedere se è verde, rosso e qual era il problema. Un utente aziendale può accedere a questa schermata e inviare i registri a un amministratore per ulteriori indagini.

Nel caso di un messaggio inviato tramite un&#39;azione personalizzata, l&#39;unica cosa che è possibile controllare durante il test di viaggio è il fatto che la chiamata del sistema dell&#39;azione personalizzata porta o meno a un errore. Se la chiamata al sistema esterno associata all&#39;azione personalizzata non genera un errore ma non provoca l&#39;invio di un messaggio, è necessario effettuare alcune indagini sul lato del sistema esterno.

