---
product: adobe campaign
title: Verifica del percorso
description: Informazioni sui test di percorso
feature: Journeys
role: User
level: Intermediate
exl-id: be413905-0631-4229-a954-80a92651206d
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '1576'
ht-degree: 7%

---

# Verifica del percorso{#testing_the_journey}

Prima di poter testare il percorso, è necessario risolvere tutti gli eventuali errori. Vedi [questa sezione](../about/troubleshooting.md#section_h3q_kqk_fhb).

Puoi testare il percorso prima della pubblicazione utilizzando i profili di test. Questo consente di analizzare il flusso dei singoli utenti nel percorso e risolvere eventuali problemi prima della pubblicazione.

Solo i profili di test possono accedere a un percorso in modalità di test. È possibile creare un nuovo profilo di test o trasformare un profilo esistente in un profilo di test. Fai riferimento a questa [sezione](../building-journeys/creating-test-profiles.md).

Per utilizzare la modalità di test, effettua le seguenti operazioni:

1. Prima di eseguire il test del percorso, verificare che sia valido e che non vi siano errori. Non sarà possibile avviare il test di un percorso con errori. Vedi [questa sezione](../about/troubleshooting.md#section_h3q_kqk_fhb). In caso di errori, viene visualizzato un simbolo di avviso.

1. Per attivare la modalità di test, fai clic sul pulsante **[!UICONTROL Test]** , situato nell’angolo in alto a destra.

   ![](../assets/journeytest1.png)

1. Utilizza il **[!UICONTROL Wait time]** nell’angolo in basso a sinistra, per definire la durata di ogni attività di attesa e timeout evento in modalità di test. Il tempo predefinito è di 10 secondi per attese e timeout di eventi. In questo modo potrai ottenere rapidamente i risultati del test. Questo parametro viene visualizzato solo se nel percorso sono state eliminate una o più attività Attendi.

   ![](../assets/journeytest_wait.png)

   >[!NOTE]
   >
   >Quando in un percorso viene utilizzato un evento di reazione con timeout, il valore predefinito e minimo del tempo di attesa è di 40 secondi. Vedi [questa sezione](../building-journeys/reaction-events.md).

1. Clic **[!UICONTROL Trigger an event]** per configurare e inviare eventi al percorso.

   ![](../assets/journeyuctest1.png)

1. Configura i diversi campi previsti. In **Identificatore profilo** , immetti il valore del campo utilizzato per identificare il profilo di test. Ad esempio, può essere l’indirizzo e-mail. Assicurati di inviare eventi relativi ai profili di test. Consulta [Attivazione degli eventi](#firing_events).

   ![](../assets/journeyuctest1-bis.png)

1. Dopo aver ricevuto gli eventi, fai clic su **[!UICONTROL Show log]** per visualizzare i risultati del test e verificarli. Consulta [Visualizzazione dei registri](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. In caso di errori, disattiva la modalità di test, modifica il percorso e verificalo di nuovo. Quando il test avrà esito positivo, potrai pubblicare il percorso. Consulta [questa pagina](../building-journeys/publishing-the-journey.md).

## Note importanti {#important_notes}

* Viene fornita un&#39;interfaccia per attivare eventi al percorso testato, ma gli eventi possono essere inviati anche da sistemi di terze parti come Postman.
* Solo i singoli utenti contrassegnati come &quot;profili di test&quot; nel servizio Profilo cliente in tempo reale potranno accedere al percorso testato. Fai riferimento a questa [sezione](../building-journeys/creating-test-profiles.md).
* La modalità di test è disponibile solo nei percorsi bozza che utilizzano uno spazio dei nomi. La modalità di test deve verificare se una persona che entra nel percorso è un profilo di test o meno e quindi deve essere in grado di raggiungere il Adobe Experience Platform.
* Il numero massimo di profili di test che può entrare in un percorso durante una sessione di test è 100.
* Quando disattivi la modalità di test, i percorsi vengono svuotati da tutte le persone che vi sono entrate in passato o che vi si trovano attualmente. Cancella anche la segnalazione.
* Puoi abilitare/disabilitare la modalità di test il numero di volte necessario.
* Non è possibile modificare il percorso quando la modalità di test è attivata. In modalità di test, puoi pubblicare direttamente il percorso; non è necessario disattivare prima la modalità di test.
* Quando si raggiunge una suddivisione, viene sempre scelto il ramo superiore. Se vuoi che il test scelga un percorso diverso, puoi riorganizzare la posizione dei rami divisi.
* Per ottimizzare le prestazioni ed evitare l’utilizzo di risorse obsolete, tutti i percorsi in modalità di test che non sono stati attivati per una settimana torneranno allo stato Bozza.

## Trasformazione di un profilo in un profilo di test{#turning-profile-into-test}

Puoi trasformare un profilo esistente in un profilo di test. In Adobe Experience Platform, puoi aggiornare gli attributi dei profili tramite chiamate API, ma non tramite l’interfaccia.

Il modo più semplice per farlo è utilizzare un **Aggiorna profilo** attività di azione e modifica il campo booleano del profilo di test da false a true. Vedi [questa sezione](../building-journeys/update-profiles.md#using-the-test-mode).

## Creazione di un profilo di test{#create-test-profile}

Se desideri creare un nuovo profilo di test, la procedura è la stessa di quando crei un profilo in Adobe Experience Platform. Viene eseguito tramite chiamate API. Consulta questa [pagina](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it)

Devi utilizzare uno schema di profilo che contiene il mixin &quot;dettagli del test del profilo&quot;. Il flag testProfile fa parte di questo mixin.

Quando crei un profilo, accertati di trasmettere il valore: testProfile = true.

Puoi anche aggiornare un profilo esistente per modificare il flag testProfile in &quot;true&quot;.

Di seguito è riportato un esempio di chiamata API per creare un profilo di test:

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```

## Attivazione degli eventi {#firing_events}

Il **[!UICONTROL Trigger an event]** consente di configurare un evento che farà entrare una persona nel percorso.

>[!NOTE]
>
>Quando si attiva un evento in modalità di test, viene generato un evento reale, che si verifica quindi anche in un altro percorso che ascolta l’evento.

Come prerequisito, è necessario sapere quali profili sono contrassegnati come profili di test in Adobe Experience Platform. In effetti, la modalità di test consente solo questi profili nel percorso e l’evento deve contenere un ID. L’ID previsto dipende dalla configurazione dell’evento. Ad esempio, può essere un ECID o un indirizzo e-mail. Il valore di questa chiave deve essere aggiunto nel **Identificatore profilo** campo.

>[!NOTE]
>
>Viene visualizzato un menu a discesa per i campi che prevedono un’enumerazione. È sufficiente selezionare uno dei valori disponibili.

Se il percorso contiene più eventi, utilizza l’elenco a discesa per selezionare un evento. Quindi, per ogni evento, configura i campi passati e l’esecuzione dell’invio dell’evento. L’interfaccia ti aiuta a trasmettere le informazioni corrette nel payload dell’evento e a verificare che il tipo di informazioni sia corretto. La modalità di test salva gli ultimi parametri utilizzati in una sessione di test per un utilizzo successivo.

![](../assets/journeytest4.png)

L’interfaccia ti consente di trasmettere parametri evento semplici. Se desideri trasmettere raccolte o altri oggetti avanzati nell’evento, puoi fare clic su **[!UICONTROL Code View]** per visualizzare l’intero codice del payload e modificarlo. Ad esempio, puoi copiare e incollare le informazioni sull’evento preparate da un utente tecnico.

![](../assets/journeytest5.png)

Un utente tecnico può inoltre utilizzare questa interfaccia per comporre payload di eventi e attivare eventi senza dover utilizzare uno strumento di terze parti.

Quando si fa clic su **[!UICONTROL Send]** , il test inizia. La progressione dell&#39;individuo nel percorso è rappresentata da un flusso visivo. Il tracciato diventa verde man mano che l&#39;individuo si sposta attraverso il percorso. Se si verifica un errore, nel passaggio corrispondente viene visualizzato un simbolo di avviso. È possibile posizionare il cursore su di esso per visualizzare ulteriori informazioni sull&#39;errore e accedere ai dettagli completi (se disponibili).

![](../assets/journeytest6.png)

Quando selezioni un profilo di test diverso nella schermata di configurazione dell’evento ed esegui di nuovo il test, il flusso visivo viene cancellato e mostra il percorso del nuovo individuo.

Quando si apre un percorso in un test, il percorso visualizzato corrisponde all’ultimo test eseguito.

Il flusso visivo funziona sia quando l’evento viene attivato tramite l’interfaccia che esternamente (ad esempio utilizzando Postman).

## Modalità di test per percorsi basati su regole {#test-rule-based}

La modalità di test è disponibile anche per i percorsi che utilizzano un evento basato su regole. Per ulteriori informazioni sugli eventi basati su regole, consulta [questa pagina](../event/about-events.md).

Quando si attiva un evento, il **Configurazione evento** La schermata ti consente di definire i parametri dell’evento da trasmettere nel test. Per visualizzare la condizione dell’ID evento, fai clic sull’icona con la descrizione comando nell’angolo in alto a destra. È inoltre disponibile una descrizione comando accanto a ogni campo che fa parte della valutazione delle regole.

![](../assets/alpha-event8.png)

Per ulteriori informazioni su come utilizzare la modalità di test, consulta [questa pagina](../building-journeys/testing-the-journey.md).

## Visualizzazione dei registri {#viewing_logs}

Il **[!UICONTROL Show log]** consente di visualizzare i risultati del test. In questa pagina vengono visualizzate le informazioni correnti del percorso in formato JSON. Un pulsante consente di copiare interi nodi. Per aggiornare i risultati dei test del percorso, è necessario aggiornare manualmente la pagina.

![](../assets/journeytest3.png)

>[!NOTE]
>
>Nei registri di test, in caso di errore durante la chiamata a un sistema di terze parti (origine dati o azione), vengono visualizzati il codice di errore e la risposta all’errore.

Viene visualizzato il numero di individui (tecnicamente denominati istanze) attualmente all’interno del percorso. Di seguito sono riportate informazioni utili visualizzate per ogni utente:

* _ID_: ID interno dell’individuo nel percorso. Può essere utilizzato a scopo di debug.
* _current step_: il passaggio in cui si trova l’individuo nel percorso. È consigliabile aggiungere etichette alle attività per identificarle più facilmente.
* _current step_ > fase: lo stato del percorso dell’individuo (in esecuzione, finito, errore o scaduto). Per ulteriori informazioni, vedi di seguito.
* _current step_ > _extraInfo_: descrizione dell’errore e altre informazioni contestuali.
* _current step_ > _fetchErrors_: informazioni sugli errori di recupero dati che si sono verificati durante questo passaggio.
* _externalKeys_: il valore della formula chiave definita nell’evento.
* _arricchedData_: i dati recuperati dal percorso se il percorso utilizza origini dati.
* _transitionHistory_: elenco dei passaggi seguiti dall’individuo. Per gli eventi, viene visualizzato il payload.
* _actionExecutionErrors_ : informazioni sugli errori che si sono verificati.

Di seguito sono riportati i diversi stati del percorso di un singolo utente:

* _In esecuzione_: l’individuo si trova attualmente nel percorso.
* _Completato_: l’individuo è alla fine del percorso.
* _Errore_: l’utente viene arrestato nel percorso a causa di un errore.
* _Timeout_: l’utente viene arrestato nel percorso a causa di un passaggio che ha richiesto troppo tempo.

Quando un evento viene attivato utilizzando la modalità di test, viene generato automaticamente un set di dati con il nome dell’origine.

Quando un evento viene attivato utilizzando la modalità di test, viene generato automaticamente un set di dati con il nome dell’origine.

La modalità di test crea automaticamente un evento esperienza e lo invia a Adobe Experience Platform. Il nome dell’origine di questo evento esperienza è &quot;Eventi test di Journey Orchestration&quot;.
