---
title: Verifica del percorso
description: 'Scopri i test di viaggio '
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
source-git-commit: 6274426ec04315149fb430b847498c0e20164bae

---


# Verifica del percorso{#testing_the_journey}

Prima di poter verificare il percorso, devi risolvere tutti gli errori, se ce ne sono. Vedere [](../about/troubleshooting.md#section_h3q_kqk_fhb).

Potete provare il viaggio prima della pubblicazione utilizzando i profili di test. Questo consente di analizzare il flusso di individui nel percorso e di risolvere eventuali problemi prima della pubblicazione.

Per utilizzare la modalità di prova, effettuate le seguenti operazioni:

1. Prima di verificare il percorso, verifica che sia valido e che non si verifichi alcun errore. Non potrai avviare un test di un viaggio con errori. Vedere [](../about/troubleshooting.md#section_h3q_kqk_fhb). In caso di errori, viene visualizzato un simbolo di avviso.

1. Per attivare la modalità di prova, fate clic sull’ **[!UICONTROL Test]** interruttore, situato nell’angolo in alto a destra.

   ![](../assets/journeytest1.png)

1. Utilizzate il parametro Tempo di **attesa nel test** , nell&#39;angolo in basso a sinistra, per definire l&#39;ora in cui ciascuna attività di attesa durerà in modalità di prova. Il tempo predefinito è 10 secondi. In questo modo sarà possibile ottenere rapidamente i risultati del test. Questo parametro viene visualizzato solo se avete abbandonato una o più attività di attesa nel viaggio.

   ![](../assets/journeytest_wait.png)

1. Fate clic **[!UICONTROL Trigger an event]** per configurare e inviare gli eventi al percorso. Assicuratevi di inviare eventi correlati ai profili di test. Consultate [Attivazione degli eventi](#firing_events).

   ![](../assets/journeyuctest1.png)

1. Dopo la ricezione degli eventi, fate clic sul **[!UICONTROL Show log]** pulsante per visualizzare il risultato del test e verificarlo. Consultate [Visualizzazione dei registri](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. In caso di errore, disattivate la modalità di prova, modificate il percorso e verificatene di nuovo il funzionamento. Quando il test è conclusivo, potete pubblicare il viaggio. Vedere [](../building-journeys/publishing-the-journey.md).

## Note importanti {#important_notes}

* Viene fornita un&#39;interfaccia per attivare gli eventi per il percorso testato, ma gli eventi possono essere inviati anche da sistemi di terze parti come Postman.
* Solo gli individui contrassegnati come &quot;profili di prova&quot; nel servizio di profilo cliente in tempo reale potranno entrare nel percorso testato. Il processo per creare un profilo di test è lo stesso del processo per creare un profilo nella piattaforma dati. È sufficiente assicurarsi che il flag del profilo di test sia vero. Puoi utilizzare la sezione Segmenti nell’interfaccia Piattaforma dati per creare un segmento di profili di test nella tua Piattaforma dati e visualizzare un elenco non esaustivo. Al momento non è possibile visualizzare l&#39;elenco completo.
* La modalità test è disponibile solo nelle bozze di viaggio che utilizzano uno spazio dei nomi. In effetti, la modalità di prova deve verificare se una persona che accede al viaggio è un profilo di prova o meno e deve quindi essere in grado di raggiungere la piattaforma dati.
* Il numero massimo di profili di test che possono entrare in un percorso durante una sessione di test è 100.
* Quando disattivate la modalità di prova, i viaggi vengono svuotati da tutte le persone che sono entrate nel passato o che vi si trovano attualmente.
* Potete attivare/disattivare la modalità di prova il numero di volte necessario.
* Non è possibile modificare il percorso quando viene attivata la modalità di prova. In modalità di prova, potete pubblicare direttamente il percorso, senza dover disattivare la modalità di prova prima.

## Configurazione degli eventi {#firing_events}

Il **[!UICONTROL Trigger an event]** pulsante consente di configurare un evento che farà entrare una persona nel percorso.

Come prerequisito, devi sapere quali profili vengono contrassegnati come profili di test nella piattaforma dati. Infatti, la modalità di prova consente solo questi profili nel percorso e l&#39;evento deve contenere un ID. L’ID previsto dipende dalla configurazione dell’evento. Ad esempio, può essere un ECID.

Se il viaggio contiene diversi eventi, utilizzate l&#39;elenco a discesa per selezionare un evento. Quindi, per ogni evento, configurate i campi passati e l’esecuzione dell’invio dell’evento. L&#39;interfaccia consente di trasmettere le informazioni corrette nel payload dell&#39;evento e verificare che il tipo di informazioni sia corretto. La modalità di prova salva gli ultimi parametri utilizzati in una sessione di prova per un uso successivo.

![](../assets/journeytest4.png)

L&#39;interfaccia consente di passare semplici parametri di evento. Se si desidera trasmettere raccolte o altri oggetti avanzati nell&#39;evento, è possibile fare clic su per visualizzare **[!UICONTROL Code View]** l&#39;intero codice del payload e modificarlo. Ad esempio, potete copiare e incollare le informazioni sull&#39;evento preparate da un utente tecnico.

![](../assets/journeytest5.png)

Un utente tecnico può anche utilizzare questa interfaccia per comporre i payload di eventi e attivare gli eventi senza dover utilizzare uno strumento di terze parti.

## Visualizzazione dei registri {#viewing_logs}

Il **[!UICONTROL Show log]** pulsante consente di visualizzare i risultati del test. In questa pagina vengono visualizzate le informazioni correnti del viaggio in formato JSON. Un pulsante consente di copiare nodi interi. Devi aggiornare manualmente la pagina per aggiornare i risultati del test del viaggio.

![](../assets/journeytest3.png)

>[!NOTE]
>
>Nei registri di test, in caso di errore durante la chiamata a un sistema di terze parti (origine dati o azione), vengono visualizzati il codice di errore e la risposta di errore.

Viene visualizzato il numero di individui (tecnicamente chiamati istanze) attualmente presenti nel percorso. Seguono alcune informazioni utili che vengono visualizzate per ciascun utente:

* _Id_: l’ID interno dell’utente durante il viaggio. Può essere utilizzato a scopo di debug.
* _currentstep_: il passo in cui si trova l&#39;individuo nel viaggio. È consigliabile aggiungere etichette alle attività per identificarle più facilmente.
* _currentstep_ > step: lo stato del viaggio (in esecuzione, completato, errore o scaduto). Per ulteriori informazioni, vedi sotto.
* _currentstep_ > _extraInfo_: descrizione dell’errore e di altre informazioni contestuali.
* _externalKeys_: il valore della formula chiave definita nell&#39;evento.
* _data_ arricchita: i dati recuperati nel caso in cui il viaggio utilizzi origini dati.
* _TransitionHistory_: l&#39;elenco dei passaggi seguiti dall&#39;utente. Per gli eventi, viene visualizzato il payload.

