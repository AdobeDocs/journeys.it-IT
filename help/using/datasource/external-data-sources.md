---
product: adobe campaign
title: Origini dati esterne
description: Informazioni su come configurare le origini dati esterne
feature: Journeys
role: User
level: Intermediate
exl-id: 9b666c15-2215-4ca5-bc72-40109749dc15
source-git-commit: 3856e323569054fac9e73f2a6af2b86518f62ab9
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 93%

---

# Origini dati esterne {#concept_t2s_kqt_52b}

Le origini dati esterne consentono di definire una connessione a sistemi di terze parti, ad esempio se si utilizza un sistema di prenotazione alberghiera per verificare se un cliente ha registrato una stanza. A differenza dell’origine dati integrata di Adobe Experience Platform, puoi creare un numero illimitato di origini dati esterne.

Sono supportate le API REST basate su POST o GET e che restituiscono JSON. Sono supportate le modalità chiave API, sia l’autenticazione di base che personalizzata.

Prendiamo l’esempio di un servizio API meteorologico che intendo sfruttare per personalizzare i comportamenti del mio percorso secondo i dati meteo in tempo reale.

Di seguito sono riportati due esempi della chiamata API:

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

La chiamata è composta da un URL principale, _https://api.adobeweather.org/weather_, due set di parametri (&quot;city&quot; per la città e &quot;lat/long&quot; per la latitudine e la longitudine) e la chiave API (appid).

Di seguito sono riportati i passaggi principali per la creazione e la configurazione di una nuova origine dati esterna:

1. Dall’elenco delle origini dati, fai clic su **[!UICONTROL Create data source]** per creare una nuova origine dati esterna.

   ![](../assets/journey25.png)

   Sul lato destro dello schermo si apre il riquadro di configurazione dell’origine dati .

   ![](../assets/journey26.png)

1. Inserisci un nome per l’origine dati.

   >[!NOTE]
   >
   >Non utilizzare spazi o caratteri speciali. Non usare più di 30 caratteri.

1. Aggiungi una descrizione all’origine dati. Questo passaggio è facoltativo.
1. Aggiungi l’URL del servizio esterno. Nel nostro esempio: _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >Per motivi di sicurezza, è consigliabile utilizzare HTTPS. Inoltre, non consentiamo l’uso di indirizzi Adobe che non siano disponibili al pubblico, né di indirizzi IP.

   ![](../assets/journey27.png)

1. Imposta l’autenticazione in base alla configurazione del servizio esterno: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** o **[!UICONTROL API key]**. Per ulteriori informazioni sulla modalità di autenticazione personalizzata, consulta [questa sezione](../datasource/external-data-sources.md#section_wjp_nl5_nhb). Le scelte del nostro esempio:


   * **[!UICONTROL Type]**: &quot;API key&quot;
   * **[!UICONTROL Value]**: &quot;1234&quot; (questo è il valore della nostra chiave API)
   * **[!UICONTROL Name]**: &quot;appid&quot; (nome del parametro della chiave API)
   * **[!UICONTROL Location]**: &quot;Query parameter&quot; (la chiave API si trova nell’URL)

   ![](../assets/journey28.png)

1. Per aggiungere un nuovo gruppo di campi per ciascun set di parametri API, fai clic su **[!UICONTROL Add a New Field Group]**. Non utilizzare spazi o caratteri speciali nel nome del gruppo di campi. Nel nostro esempio, dobbiamo creare due gruppi di campi, uno per ciascun insieme di parametri (city e long/lat).

Per il set di parametri &quot;long/lat&quot;, viene creato un gruppo di campi con le seguenti informazioni:

* **[!UICONTROL Used in]**: visualizza il numero di percorsi che utilizzano un gruppo di campi. Puoi fare clic sull’icona **[!UICONTROL View journeys]** per visualizzare l’elenco dei percorsi che utilizzano questo gruppo di campi.
* **[!UICONTROL Method]**: seleziona il metodo POST o GET. Nel nostro caso, scegliamo il metodo GET.
* **[!UICONTROL Response Payload]**: fai clic all’interno del campo **[!UICONTROL Payload]** e incolla un esempio del payload restituito dalla chiamata. Per il nostro esempio, abbiamo utilizzato un payload trovato su un sito web API per il meteo. Verifica la correttezza dei tipi di campi. Ogni volta che viene chiamata l’API, il sistema recupererà tutti i campi inclusi nell’esempio di payload. Se vuoi modificare il payload attualmente trasmesso, è possibile fare clic su **[!UICONTROL Paste a new payload]**.
* **[!UICONTROL Dynamic Values]**: inserisci i diversi parametri separati da una virgola, nel nostro esempio &quot;long,lat&quot;. Poiché i valori del parametro dipendono dal contesto di esecuzione, saranno definiti all’interno dei percorsi. Consulta [questa pagina](../expression/expressionadvanced.md).
* **[!UICONTROL Sent Payload]**: questo campo non viene visualizzato nel nostro esempio. È disponibile solo se si seleziona il metodo POST. Incolla il payload che verrà inviato al sistema di terze parti.

In presenza di una chiamata GET che richieda i parametri, inseriscili nel campo **[!UICONTROL Dynamic Values]** e verranno aggiunti automaticamente alla fine della chiamata. Nel caso di una chiamata POST, è necessario:

* Elencare i parametri da trasmettere al momento della chiamata nel campo **[!UICONTROL Dynamic Values]**, nell’esempio seguente: &quot;identifier&quot;.
* Specificare i parametri anche utilizzando la medesima sintassi nel corpo del payload inviato. A tale scopo, è necessario aggiungere: &quot;param&quot;: “nome del tuo parametro”, nell’esempio seguente è &quot;identifier&quot;. Attieniti alla sintassi seguente:

   ```
   {"id":{"param":"identifier"}}
   ```

![](../assets/journey29.png)

Fai clic su **[!UICONTROL Save]**.

L’origine dati è ora configurata ed è pronta per essere utilizzata nei percorsi, ad esempio nelle tue condizioni o per personalizzare un’e-mail. Se la temperatura è superiore a 30°C, puoi decidere di inviare una comunicazione specifica.

## Modalità di autenticazione personalizzata{#section_wjp_nl5_nhb}

>[!CONTEXTUALHELP]
>id="jo_authentication_payload"
>title="Informazioni sull’autenticazione personalizzata"
>abstract="La modalità di autenticazione personalizzata viene utilizzata per l’autenticazione complessa destinata al richiamo dei protocolli di wrapping di API come OAuth2. L’esecuzione dell’azione è un processo suddiviso in due fasi. Innanzitutto, viene eseguita una chiamata all’endpoint per la generazione del token di accesso. Quindi, il token di accesso viene inserito nella richiesta HTTP dell’azione."

Questa modalità di autenticazione viene utilizzata per la tipologia complessa, spesso impiegata per la chiamata dei protocolli di wrapping API come OAuth2 e per il recupero di un token di accesso da inserire nella richiesta HTTP effettiva per l’azione.

Quando configuri l’autenticazione personalizzata, puoi fare clic sul pulsante seguente per verificare la corretta configurazione del payload di autenticazione personalizzata.

![](../assets/journey29-bis.png)

Se il test ha esito positivo, il pulsante diventa verde.

![](../assets/journey29-ter.png)

Con questa autenticazione, l’esecuzione dell’azione è un processo suddiviso in due fasi:

1. Chiama l’endpoint per generare il token di accesso.
1. Chiama l’API REST inserendo il token di accesso nel modo appropriato.

Questa autenticazione è costituita da due parti.

Definizione dell’endpoint da chiamare per la generazione del token di accesso:

* endpoint: URL da utilizzare per generare l’endpoint
* metodo della richiesta HTTP sull’endpoint (GET o POST)
* intestazioni: coppie chiave/valore da inserire come intestazioni in questa chiamata, se necessario
* corpo: descrive il corpo della chiamata se il metodo è POST. Supportiamo una struttura del corpo limitata, definita in bodyParams (coppie chiave/valore). Il bodyType descrive il formato e la codifica del corpo nella chiamata:
   * &#39;form&#39;: significa che il tipo di contenuto sarà application/x-www-form-urlencoded (charset UTF-8) e che le coppie chiave/valore saranno serializzate come segue: key1=value1&amp;key2=value2&amp;...
   * &#39;json&#39;: indica che il tipo di contenuto sarà application/json (charset UTF-8) e che le coppie di valori chiave saranno serializzate così come sono, come oggetto json: _{ &quot;key1&quot;: &quot;value1&quot;, &quot;key2&quot;: &quot;value2&quot;, ...}_

La definizione della modalità di inserimento del token di accesso nella richiesta HTTP dell’azione:

* authorizationType: definisce il modo in cui il token di accesso generato deve essere inserito nella chiamata HTTP per l’azione. I valori possibili sono:

   * bearer: indica che il token di accesso deve essere inserito nell’intestazione Autorizzazione, ad esempio: _Authorization: Bearer &lt;token di accesso>_
   * header: indica che il token di accesso deve essere inserito come intestazione, il nome dell’intestazione è definito dalla proprietà tokenTarget. Ad esempio, se tokenTarget è myHeader, il token di accesso verrà inserito come intestazione: _myHeader: &lt;token di accesso>_
   * queryParam: indica che il token di accesso deve essere inserito come queryParam, il nome del param di query è definito dalla proprietà tokenTarget. Ad esempio, se il tokenTarget è myQueryParam, l’URL della chiamata di azione sarà: _&lt;url>?myQueryParam=&lt;token di accesso>_

* tokenInResponse: indica come estrarre il token di accesso dalla chiamata di autenticazione. Questa proprietà può corrispondere a:
   * &#39;response&#39;: indica che la risposta HTTP è il token di accesso.
   * Un selettore in un json: poiché la risposta deve essere un json, non sono supportati altri formati come XML. Il formato di questo selettore è _json://&lt;percorso della proprietà del token di accesso>_. Ad esempio, se la risposta della chiamata è: _{ &quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 12323445656}_, tokenInResponse sarà: _json: //access_token_

Il formato di questa autenticazione è:

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers": {
        "<header name>": "<header value>",
        ...
    },
    (optional, mandatory if method is 'POST') "body": {
        "bodyType": "<'form'or 'json'>,
        "bodyParams": {
            "param1": value1,
            ...

        }
    },
    "tokenInResponse": "<'response' or json selector in format 'json://<field path to access token>'"
}
```

Adesso puoi modificare la durata della cache del token per un’origine dati di autenticazione personalizzata. Di seguito è riportato un esempio di payload di autenticazione personalizzato. La durata della cache è definita nel parametro “cacheDuration”. Tale parametro Specifica la durata di conservazione del token generato nella cache. L’unità può essere in millisecondi, secondi, minuti, ore, giorni, mesi, anni.

```
"authentication": {
    "type":"customAuthorization",
    "authorizationType":"Bearer",
    "endpoint":"http://localhost:${port}/epsilon/oauth2/access_token",
    "method":"POST",
    "headers": {
        "Authorization":"Basic EncodeBase64(${epsilonClientId}:${epsilonClientSecret})"
        },
    "body": {
        "bodyType":"form",
        "bodyParams": {
             "scope":"cn mail givenname uid employeeNumber",
             "grant_type":"password",
             "username":"${epsilonUserName}",
             "password":"${epsilonUserPassword}"
             }
        },
    "tokenInResponse":"json://access_token",
    "cacheDuration":
             { "duration":5, "timeUnit":"seconds" }
    }
```

>[!NOTE]
>
>La durata della cache consente di evitare un numero eccessivo di chiamate agli endpoint di autenticazione. La conservazione dei token di autenticazione è memorizzata nella cache dei servizi, non vi è persistenza. Se un servizio viene riavviato, inizia con una cache pulita. Per impostazione predefinita, la durata della cache è di 1 ora. Nel payload di autenticazione personalizzata, può essere adattato specificando un’altra durata di conservazione.
