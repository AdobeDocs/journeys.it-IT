---
product: adobe campaign
solution: Journey Orchestration
title: Capping della descrizione API
description: Ulteriori informazioni sull'API Capping.
products: journeys
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 1%

---


# Utilizzo dell’API Capping

## Introduzione

[!DNL Journey Orchestration]Le API API di Microsoft supportano 5000 eventi/secondi, ma alcuni sistemi o API esterni non possono avere un throughput equivalente. Ecco perché [!DNL Journey Orchestration] viene fornito con una funzione dedicata denominata API di cattura per monitorare e limitare la velocità che imponiamo ai sistemi esterni.

Durante una configurazione dell&#39;origine dati, definirai una connessione a un sistema per recuperare informazioni aggiuntive che verranno utilizzate nei tuoi viaggi, o per una definizione dell&#39;azione, configurerai la connessione di un sistema di terze parti per inviare messaggi o chiamate API. Ogni volta che una chiamata API viene eseguita da Journey, l&#39;API di capping viene interrogata, la chiamata viene eseguita tramite il motore API. In presenza di un limite definito, la chiamata viene rifiutata e il sistema esterno non verrà sovraccaricato.

Per ulteriori informazioni sulla configurazione delle azioni o delle origini dati, vedere [Informazioni sulle azioni](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) o [Informazioni sulle origini dati](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## Resources

>[!NOTE]
>
>L&#39; [!DNL Journey Orchestration] API Capping è descritta all&#39;interno di un file Swagger disponibile [qui](https://adobedocs.github.io/JourneyAPI/docs/).

Per utilizzare questa API con l&#39;istanza [!DNL Journey Orchestration], è necessario utilizzare la console AdobeI/O. Per iniziare, seguire la [Guida introduttiva a  Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) e utilizzare le sezioni presenti in questa pagina.

Per verificare e preparare l&#39;integrazione, è disponibile una raccolta Postman [qui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Autenticazione

### Impostazione dell’accesso API

[!DNL Journey Orchestration] L&#39;accesso alle API è configurato tramite i passaggi descritti di seguito. Ciascuno di questi passaggi è descritto nella [ documentazione Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Per gestire i certificati in  Adobe I/O, accertatevi di disporre dei diritti di <b>amministratore di sistema</b> nell&#39;organizzazione o di un account [sviluppatore](https://helpx.adobe.com/enterprise/using/manage-developers.html) nell&#39;Admin Console.

1. **Verificate di disporre di un certificato** digitale oppure createne uno, se necessario. Le chiavi pubblica e privata fornite con il certificato sono necessarie nei seguenti passaggi.
1. **Crea una nuova integrazione con  [!DNL Journey Orchestration]** Servicein  Adobe I/O e configurala. L&#39;accesso al profilo di prodotto è necessario per [!DNL Journey Orchestration] e Adobe Experience Platform. Le credenziali verranno quindi generate (Chiave API, Segreto cliente...).
1. **Create un token Web JSON (JWT)** dalle credenziali generate in precedenza e firmatelo con la vostra chiave privata. Il JWT codifica tutte le informazioni di identità e sicurezza necessarie per  Adobe per verificare la propria identità e concedere l&#39;accesso all&#39;API. Questo passaggio è dettagliato in questa sezione [sezione](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Scambiare il JWT per un** Token di accesso tramite una richiesta di POST o tramite l&#39;interfaccia della console per sviluppatori. Questo token di accesso dovrà essere utilizzato in ogni intestazione delle richieste API.

Per stabilire una sessione di servizio sicura  Adobe I/O API, ogni richiesta a un servizio  Adobe deve includere nell’intestazione Autorizzazione le informazioni riportate di seguito.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Si tratta dell’ID organizzazione personale, un ID organizzazione viene fornito dal Adobe  per ogni istanza:

   * &lt;organization> : l&#39;istanza di produzione

   Per ottenere il valore ID ORGANIZZAZIONE, rivolgiti all’amministratore o al contatto tecnico  Adobe. È inoltre possibile recuperarlo in  Adobe I/O quando si crea una nuova integrazione, nell&#39;elenco delle licenze (vedere la <a href="https://www.adobe.io/authentication.html"> documentazione Adobe I/O</a>).

* **&lt;access_token>**: Token di accesso personale, che è stato recuperato durante lo scambio del JWT tramite una richiesta di POST.

* **&lt;api_key>**: la chiave API personale. Viene fornito in  Adobe I/O dopo la creazione di una nuova integrazione in [!DNL Journey Orchestration] Service.



## Capping della descrizione API

L’API Capping consente di creare, configurare e monitorare le configurazioni di capping.

| Metodo | Percorso | Descrizione |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Ottenere un elenco delle configurazioni di capping dell&#39;endpoint |
| [!DNL POST] | /endpointConfigs | Creare una configurazione di cappottatura dell&#39;endpoint |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploying | Implementare una configurazione di cappottatura dell&#39;endpoint |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeployment | Disdistribuire una configurazione di cappottatura dell&#39;endpoint |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | Verificate se è possibile distribuire o meno una configurazione di cappotto dell&#39;endpoint |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Aggiornare una configurazione di cappottatura dell&#39;endpoint |
| [!DNL GET] | /endpointConfigs/`{uid}` | Recuperare una configurazione di capping endpoint |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Eliminare una configurazione di codifica enpoint |

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

Quando viene chiamato un metodo **canDeploy**, il processo convalida la configurazione e restituisce lo stato di convalida identificato dal relativo ID univoco:

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
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nome servizio non valido  `<!--<given value>-->`: deve essere &#39;dataSource&#39; o &#39;action&#39;


L&#39;avviso potenziale è il seguente:

**ERR_ENDPOINTCONFIG_106**: configurazione di capping: max connessioni HTTP non definite: nessuna limitazione per impostazione predefinita



## Casi di utilizzo

In questa sezione sono elencati i cinque casi d&#39;uso principali che è possibile eseguire per gestire la configurazione di capping in [!DNL Journey Orchestration].

Per facilitare il test e la configurazione, è disponibile una raccolta Postman [qui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Questa raccolta Postman è stata impostata per condividere la raccolta Postman Variable generata tramite __[Adobe I/O Console&#39;s Integrations](https://console.adobe.io/integrations) > Try it out > Download for Postman__, che genera un file Postman Environment con i valori di integrazioni selezionati.

Una volta scaricati e caricati in Postman, è necessario aggiungere tre variabili: `{JO_HOST}`,`{Base_Path}` e `{SANDBOX_NAME}`.
* `{JO_HOST}` :  [!DNL Journey Orchestration] URL gateway
* `{BASE_PATH}` : punto di ingresso per l&#39;API. Il valore è &#39;/authoring&#39;
* `{SANDBOX_NAME}` : l’intestazione  **x-sandbox-name**  (ad esempio, &#39;prod&#39;) corrispondente al nome della sandbox in cui avranno luogo le operazioni API. Per ulteriori informazioni, consultate la [panoramica sulle sandbox](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html).

Nella sezione seguente, troverete l&#39;elenco delle chiamate API rimanenti ordinate per eseguire il caso d&#39;uso.

Caso d’uso n° 1: **Creazione e implementazione di una nuova configurazione di capping**

1. list
1. create
1. canonizzare
1. distribuire

Caso d’uso n°2: **Aggiornare e distribuire una configurazione di caption non ancora distribuita**

1. list
1. get
1. update
1. canonizzare
1. distribuire

Caso d’uso n° 3: **Disdistribuire ed eliminare una configurazione di caption distribuita**

1. list
1. non distribuire
1. delete

Caso d’uso n°4: **Eliminare una configurazione di tappatura distribuita.**

In una sola chiamata API, potete annullare la distribuzione ed eliminare la configurazione utilizzando il parametro forceDelete.
1. list
1. delete, with forceDelete param

Caso d’uso n° 5: **Aggiornamento di una configurazione di tappatura già implementata**

1. list
1. get
1. update
1. non distribuire
1. canonizzare
1. distribuire

