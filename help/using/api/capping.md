---
title: Capping della descrizione API
description: Ulteriori informazioni sull'API Capping.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9f28bdc0e74359ff9f8d84961769b84973ae3f39
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 1%

---


# Utilizzo dell’API Capping

## Introduzione

Le API dell&#39;orchestrazione del percorso supportano 5000 eventi/secondi, ma alcuni sistemi o API esterni non possono avere un throughput equivalente. Ecco perché l&#39;orchestrazione del viaggio viene fornita con una funzione dedicata denominata API di maschiatura per monitorare e limitare la velocità che imponiamo ai sistemi esterni.

Durante una configurazione dell&#39;origine dati, definirai una connessione a un sistema per recuperare informazioni aggiuntive che verranno utilizzate nei tuoi viaggi, o per una definizione dell&#39;azione, configurerai la connessione di un sistema di terze parti per inviare messaggi o chiamate API. Ogni volta che una chiamata API viene eseguita da Journey, l&#39;API di capping viene interrogata, la chiamata viene eseguita tramite il motore API. In presenza di un limite definito, la chiamata viene rifiutata e il sistema esterno non verrà sovraccaricato.

Per ulteriori informazioni sulla configurazione delle azioni o delle origini dati, vedere [Informazioni sulle azioni](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) o [Informazioni sulle origini dati](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## Risorse

L&#39;API di mappatura dell&#39;orchestrazione del percorso è descritta all&#39;interno di un file Swagger disponibile [qui](https://adobedocs.github.io/JourneyAPI/docs/).

Per utilizzare questa API con l&#39;istanza di orchestrazione del percorso, è necessario utilizzare la console AdobeIO. Per iniziare, segui questa [Guida introduttiva ad Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) e utilizza le sezioni presenti in questa pagina.

Per verificare e preparare l&#39;integrazione, è disponibile [qui](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)una raccolta Postman.

## Autenticazione

### Impostazione dell’accesso API

L&#39;accesso alle API di orchestrazione del percorso è configurato attraverso i passaggi indicati di seguito. Ciascuno di questi passaggi è descritto dettagliatamente nella documentazione [di](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe IO.

>[!CAUTION]
>
>Per gestire i certificati in Adobe IO, accertatevi di disporre dei diritti di amministratore <b>di</b> sistema sull&#39;organizzazione o su un account <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html"></a> sviluppatore nell&#39;Admin Console.

1. **Verificate di disporre di un certificato** digitale oppure createne uno, se necessario. Le chiavi pubblica e privata fornite con il certificato sono necessarie nei seguenti passaggi.
1. **Crea una nuova integrazione con il servizio** di orchestrazione del percorso in Adobe IO e configurala. L&#39;accesso al profilo di prodotto è necessario per l&#39;orchestrazione del percorso e per Adobe Experience Platform. Le credenziali verranno quindi generate (Chiave API, Segreto cliente...).
1. **Create un token Web JSON (JWT)** dalle credenziali generate in precedenza e firmatelo con la vostra chiave privata. Il JWT codifica tutte le informazioni di identità e sicurezza necessarie ad Adobe per verificare la tua identità e concederti l&#39;accesso all&#39;API. Questo passaggio è dettagliato in questa [sezione](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Scambiate il JWT per ottenere un token** di accesso tramite una richiesta POST o tramite l&#39;interfaccia della console per sviluppatori. Questo token di accesso dovrà essere utilizzato in ogni intestazione delle richieste API.

Per stabilire una sessione dell&#39;API Adobe I/O sicura per il servizio, ogni richiesta a un servizio Adobe deve includere nell&#39;intestazione Autorizzazione le informazioni riportate di seguito.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZZAZIONE>**: Questo è l’ID organizzazione personale, un ID organizzazione viene fornito da Adobe per ogni istanza:

   * &lt;ORGANIZZAZIONE> : l&#39;istanza di produzione
   Per ottenere il valore ID ORGANIZZAZIONE, rivolgiti all’amministratore o al contatto tecnico Adobe. È inoltre possibile recuperarlo in Adobe I/O al momento della creazione di una nuova integrazione, nell&#39;elenco delle licenze (consultare la documentazione <a href="https://www.adobe.io/authentication.html">di</a>Adobe IO).

* **&lt;ACCESS_TOKEN>**: Il token di accesso personale, che è stato recuperato durante lo scambio del JWT tramite una richiesta POST.

* **&lt;API_KEY>**: la chiave API personale. Viene fornito in Adobe I/O dopo la creazione di una nuova integrazione con il servizio di orchestrazione del percorso.



## Capping della descrizione API

L’API Capping consente di creare, configurare e monitorare le configurazioni di capping.

| Metodo | Percorso | Descrizione |
|---|---|---|
| POST | list/endpointConfigs | Ottenere un elenco delle configurazioni di capping dell&#39;endpoint |
| POST | /endpointConfigs | Creare una configurazione di cappottatura dell&#39;endpoint |
| POST | /endpointConfigs/{uid}/deploying | Implementare una configurazione di cappottatura dell&#39;endpoint |
| POST | /endpointConfigs/{uid}/undeployment | Disdistribuire una configurazione di cappottatura dell&#39;endpoint |
| POST | /endpointConfigs/{uid}/canDeploy | Verificate se è possibile distribuire o meno una configurazione di cappotto dell&#39;endpoint |
| PUT | /endpointConfigs/{uid} | Aggiornare una configurazione di cappottatura dell&#39;endpoint |
| GET | /endpointConfigs/{uid} | Recuperare una configurazione di capping endpoint |
| ELIMINA | /endpointConfigs/{uid} | Eliminare una configurazione di codifica enpoint |

Quando si crea o aggiorna una configurazione, viene automaticamente eseguito un controllo per garantire la sintassi e l&#39;integrità del payload.
In caso di problemi, l&#39;operazione restituisce un avviso o degli errori per facilitare la correzione della configurazione.



## Configurazione endpoint

Di seguito è riportata la struttura di base di una configurazione di endpoint:

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### Esempio:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```


## Avvisi ed errori

Quando viene chiamato un metodo **canDeploy** , il processo convalida la configurazione e restituisce lo stato di convalida identificato dal relativo ID univoco:

```
"ok" or "error"
```

Gli errori potenziali sono:

* **ERR_ENDPOINTCONFIG_100**: configurazione di capping: url mancante o non valido
* **ERR_ENDPOINTCONFIG_101**: configurazione di capping: url non valido
* **ERR_ENDPOINTCONFIG_102**: configurazione di capping: url non valido: il carattere jolly nell&#39;URL non è consentito in host:port
* **ERR_ENDPOINTCONFIG_103**: configurazione di capping: metodi HTTP mancanti
* **ERR_ENDPOINTCONFIG_104**: configurazione di capping: nessuna classificazione di chiamata definita
* **ERR_ENDPOINTCONFIG_107**: configurazione di capping: numero massimo di chiamate non valido (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: configurazione di capping: numero massimo di chiamate non valido (puntoInMs)
* **ERR_ENDPOINTCONFIG_111**: configurazione di capping: impossibile creare la configurazione dell&#39;endpoint: payload non valido
* **ERR_ENDPOINTCONFIG_112**: configurazione di capping: impossibile creare la configurazione dell&#39;endpoint: attesa di un payload JSON
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nome servizio non valido <!--<given value>-->: deve essere &#39;dataSource&#39; o &#39;action&#39;


L&#39;avviso potenziale è il seguente:

**ERR_ENDPOINTCONFIG_106**: configurazione di capping: max connessioni HTTP non definite: nessuna limitazione per impostazione predefinita



## Casi di utilizzo

In questa sezione sono elencati i cinque casi d’uso principali che è possibile eseguire per gestire la configurazione di capping nell’Orchestrazione del percorso.

Per facilitare il test e la configurazione, è disponibile [qui](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)una raccolta Postman.

Questa raccolta Postman è stata impostata per condividere la raccolta Postman Variabile generata tramite Integrazioni __[della console](https://console.adobe.io/integrations)Adobe I/O > Prova > Scarica per Postman__, che genera un file Postman Environment con i valori di integrazioni selezionati.

Una volta scaricati e caricati in Postman, è necessario aggiungere due variabili: `{JO_HOST}` e `{Base_Path}`.
* `{JO_HOST}` : URL gateway di orchestrazione viaggio
* `{BASE_PATH}` : punto di ingresso per l&#39;API. Il valore è &#39;/authoring&#39;



Caso d’uso n° 1: **Creazione e implementazione di una nuova configurazione di capping**

1. list
1. create
1. canonizzare
1. distribuire

Caso d’uso n°2: **Aggiornare e distribuire una configurazione di cappottatura non ancora distribuita**

1. list
1. get
1. update
1. canonizzare
1. distribuire

Caso d’uso n° 3: **Disdistribuire ed eliminare una configurazione di capping distribuita**

1. list
1. non distribuire
1. delete

Caso d’uso n°4: **Eliminare una configurazione di capping distribuita.**

In una sola chiamata API, potete annullare la distribuzione ed eliminare la configurazione utilizzando il parametro forceDelete.
1. list
1. delete, with forceDelete param

Caso d’uso n° 5: **Aggiornare una configurazione di cappotting già distribuita**

1. list
1. get
1. update
1. non distribuire
1. canonizzare
1. distribuire

