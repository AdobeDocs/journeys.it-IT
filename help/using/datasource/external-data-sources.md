---
title: 'Origini dati esterne '
description: 'Scopri come configurare origini dati esterne '
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
source-git-commit: a1c4eed8360efcbfcaa5e54c8831e1a4b2ecc02e

---



# Origini dati esterne {#concept_t2s_kqt_52b}

Le origini dati esterne consentono di definire una connessione a sistemi di terze parti, ad esempio se si utilizza un sistema di prenotazione alberghiera per verificare se la persona ha registrato una stanza. Invece dell’origine dati integrata della piattaforma Experience, puoi creare un numero illimitato di origini dati esterne.

Sono supportate le API REST che utilizzano POST o GET e che restituiscono JSON. Sono supportate le modalità di autenticazione API Key, di base e personalizzate.

Prendiamo l&#39;esempio di un servizio API meteorologico che voglio usare per personalizzare i comportamenti del mio viaggio in base ai dati meteo in tempo reale.

Di seguito sono riportati due esempi della chiamata API:

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

La chiamata è composta da un URL principale (_https://api.adobeweather.org/weather_), due set di parametri (&quot;città&quot; per la città e &quot;lat/long&quot; per la latitudine e la longitudine) e la chiave API (appid).

Di seguito sono riportati i passaggi principali per creare e configurare una nuova origine dati esterna:

1. Dall&#39;elenco delle origini dati, fare clic **[!UICONTROL Add]** per creare una nuova origine dati esterna.

   ![](../assets/journey25.png)

   Viene aperto il riquadro di configurazione dell&#39;origine dati sul lato destro dello schermo.

   ![](../assets/journey26.png)

1. Immettere un nome per l&#39;origine dati.

   >[!NOTE]
   >
   >Non utilizzate spazi o caratteri speciali. Non utilizzare più di 30 caratteri.

1. Aggiungi una descrizione all&#39;origine dati. Questo passaggio è facoltativo.
1. Aggiungete l&#39;URL del servizio esterno. Nel nostro esempio: _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >È consigliabile utilizzare HTTPS per motivi di sicurezza. Inoltre, non consentiamo l&#39;uso di indirizzi Adobe che non sono disponibili al pubblico e l&#39;uso di indirizzi IP.

   ![](../assets/journey27.png)

1. Configurare l&#39;autenticazione in base alla configurazione del servizio esterno: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** o **[!UICONTROL API key]**. Per ulteriori informazioni sulla modalità di autenticazione personalizzata, vedere [](../datasource/external-data-sources.md#section_wjp_nl5_nhb). Nel nostro esempio, scegliamo:


   * **[!UICONTROL Type]**: &quot;Chiave API&quot;
   * **[!UICONTROL Value]**: &quot;1234&quot; (questo è il valore della nostra chiave API)
   * **[!UICONTROL Name]**: &quot;appid&quot; (nome del parametro chiave API)
   * **[!UICONTROL Location]**: &quot;Parametro query&quot; (la chiave API si trova nell&#39;URL)
   ![](../assets/journey28.png)

1. Aggiungete un nuovo gruppo di campi per ciascun set di parametri API facendo clic su **[!UICONTROL Add a New Field Group]**. Non utilizzate spazi o caratteri speciali nel nome del gruppo di campi. Nel nostro esempio, dobbiamo creare due gruppi di campi, uno per ciascun insieme di parametri (città e long/lat).

Per il set di parametri &quot;long/lat&quot;, viene creato un gruppo di campi con le seguenti informazioni:

* **[!UICONTROL Used in]**: visualizza il numero di viaggi che utilizzano un gruppo di campi. Puoi fare clic sull&#39; **[!UICONTROL View journeys]** icona per visualizzare l&#39;elenco dei viaggi utilizzando questo gruppo di campi.
* **[!UICONTROL Method]**: selezionate il metodo POST o GET. Nel nostro caso, selezioniamo il metodo GET.
* **[!UICONTROL Cache duration]**: nel nostro caso, vogliamo che il tempo sia memorizzato nella cache per 10 minuti.
* **[!UICONTROL Response Payload]**: fai clic all’interno del **[!UICONTROL Payload]** campo e incolla un esempio del payload restituito dalla chiamata. Per il nostro esempio, abbiamo utilizzato un payload trovato su un sito web API per il tempo. Verificare che i tipi di campo siano corretti. Ogni volta che viene chiamata l&#39;API, il sistema recupererà tutti i campi inclusi nell&#39;esempio di payload. È possibile fare clic su **[!UICONTROL Paste a new payload]** se si desidera modificare il payload attualmente passato.
* **[!UICONTROL Dynamic Values]**: inserire i diversi parametri separati da un coma, &quot;long,lat&quot; nel nostro esempio. Poiché i valori dei parametri dipendono dal contesto di esecuzione, saranno definiti nei viaggi. Vedere [](../expression/expressionadvanced.md).
* **[!UICONTROL Sent Payload]**: questo campo non viene visualizzato nel nostro esempio. È disponibile solo se si seleziona il metodo POST. Incolla il payload che verrà inviato al sistema di terze parti.

In caso di chiamata GET che richieda parametri, immetti i parametri nel **[!UICONTROL Parameters]** campo e questi vengono automaticamente aggiunti alla fine della chiamata. In caso di chiamata POST, è necessario:

* elencare i parametri da passare al momento della chiamata nel **[!UICONTROL Parameter]** campo (nell&#39;esempio seguente: &quot;identifier&quot;).
* specificarli anche con la stessa sintassi nel corpo del payload inviato. A tale scopo, è necessario aggiungere: &quot;param&quot;: &quot;name of your parameter&quot; (nel seguente esempio: &quot;identifier&quot;). Seguite la sintassi seguente:

   ```
   {"id":{"param":"identifier"}}
   ```

![](../assets/journey29.png)

Clic **[!UICONTROL Save]**.

L&#39;origine dati è ora configurata e pronta per essere utilizzata nei viaggi, ad esempio nelle tue condizioni o per personalizzare un&#39;e-mail. Se la temperatura è superiore a 30°C, si può decidere di inviare una comunicazione specifica.

## Modalità autenticazione personalizzata{#section_wjp_nl5_nhb}

>[!CONTEXTUALHELP]
>id=&quot;jo_authentication_payload&quot;
>title=&quot;Informazioni sull&#39;autenticazione personalizzata&quot;
>abstract=&quot;La modalità di autenticazione personalizzata viene utilizzata per l&#39;autenticazione complessa per chiamare i protocolli di wrapping API come OAuth2. L&#39;esecuzione dell&#39;azione è un processo in due fasi. Innanzitutto, viene eseguita una chiamata all&#39;endpoint per generare il token di accesso. Quindi, il token di accesso viene inserito nella richiesta HTTP dell’azione.&quot;

Questa modalità di autenticazione viene utilizzata per l&#39;autenticazione complessa, frequentemente utilizzata per chiamare i protocolli di wrapping API come OAuth2, per recuperare un token di accesso da inserire nella richiesta HTTP reale per l&#39;azione.

Quando configurate l&#39;autenticazione personalizzata, potete fare clic sul pulsante qui sotto per verificare se il payload di autenticazione personalizzato è configurato correttamente.

![](../assets/journey29-bis.png)

Se il test ha esito positivo, il pulsante diventa verde.

![](../assets/journey29-ter.png)

Con questa autenticazione, l&#39;esecuzione dell&#39;azione è un processo in due fasi:

1. Chiama l’endpoint per generare il token di accesso.
1. Chiama l&#39;API REST inserendo nel modo appropriato il token di accesso.

Questa autenticazione ha due parti.

Definizione dell&#39;endpoint da chiamare per generare il token di accesso:

* endpoint: URL da usare per generare l’endpoint
* della richiesta HTTP sull&#39;endpoint (GET o POST)
* intestazioni: coppie chiave/valore da inserire come intestazioni in questa chiamata, se necessario
* corpo: descrive il corpo della chiamata se il metodo è POST. Supportiamo una struttura del corpo limitata, definita in bodyParams (coppie chiave/valore). Il bodyType descrive il formato e la codifica del corpo nella chiamata:
   * &#39;form&#39;: il che significa che il tipo di contenuto sarà application/x-www-form-urlencoded (charset UTF-8) e che le coppie chiave/valore saranno serializzate come segue: key1=value1&amp;key2=value2&amp;...
   * &#39;json&#39;: il che significa che il tipo di contenuto sarà application/json (charset UTF-8) e che le coppie di valori chiave saranno serializzate come oggetto json così come sono: _{ &quot;key1&quot;: &quot;value1&quot;, &quot;key2&quot;: &quot;value2&quot;, ...}_

Definizione della modalità di inserimento del token di accesso nella richiesta HTTP dell’azione:

* authorizedType: definisce il modo in cui il token di accesso generato deve essere inserito nella chiamata HTTP per l’azione. I valori possibili sono:

   * portatore: indica che il token di accesso deve essere inserito nell’intestazione Autorizzazione, ad esempio: _Autorizzazione: Portatore &lt;token di accesso>_
   * header: indica che il token di accesso deve essere inserito come intestazione, il nome dell&#39;intestazione definito dalla proprietà tokenTarget. Ad esempio, se tokenTarget è myHeader, il token di accesso verrà inserito come intestazione come: _myHeader: &lt;token di accesso>_
   * queryParam: indica che il token di accesso deve essere inserito come queryParam, il nome del param di query definito dalla proprietà tokenTarget. Ad esempio, se il tokenTarget è myQueryParam, l’URL della chiamata di azione sarà: _&lt;url>?myQueryParam=&lt;token di accesso>_

* tokenInResponse: indica come estrarre il token di accesso dalla chiamata di autenticazione. Questa proprietà può essere:
   * &#39;response&#39;: indica che la risposta HTTP è il token di accesso
   * un selettore in un json (supponendo che la risposta sia un json, non sono supportati altri formati come XML). Il formato di questo selettore è _json://&lt;percorso della proprietà del token di accesso>_. Ad esempio, se la risposta della chiamata è: _{ &quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 12323445656}_, tokenInResponse sarà: _json: //access_token_

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
