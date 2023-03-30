---
product: adobe campaign
title: Limitazione della descrizione API
description: Ulteriori informazioni sull’API di limitazione di utilizzo.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 1f91bae24dfcb291dd354e4bff9eab85afdaf5a1
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 3%

---


# Utilizzare l’API di limitazione di utilizzo {#work}

L’API di limitazione di utilizzo consente di creare, configurare e monitorare le configurazioni di limitazione di utilizzo.

## Limitazione della descrizione API

| Metodo | Path | Descrizione |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Ottieni un elenco delle configurazioni di limiti endpoint |
| [!DNL POST] | /endpointConfigs | Creare una configurazione di limite endpoint |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | Distribuzione di una configurazione di limite endpoint |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | Disdistribuire una configurazione di limite endpoint |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | Controlla se è possibile distribuire o meno una configurazione di limite endpoint |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Aggiornare una configurazione di limite endpoint |
| [!DNL GET] | /endpointConfigs/`{uid}` | Recuperare una configurazione di limite endpoint |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Eliminare una configurazione di limite di livello |

Quando una configurazione viene creata o aggiornata, viene eseguito automaticamente un controllo per garantire la sintassi e l’integrità del payload.
Se si verificano alcuni problemi, l&#39;operazione restituisce un avviso o degli errori per facilitare la correzione della configurazione.

## Configurazione endpoint

La struttura di base di una configurazione dell’endpoint è la seguente:

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

Quando un **canDeploy** viene chiamato , il processo convalida la configurazione e restituisce lo stato di convalida identificato dal relativo ID univoco:

```
"ok" or "error"
```

Gli errori potenziali sono:

* **ERR_ENDPOINTCONFIG_100**: configurazione di tappping: url mancante o non valido
* **ERR_ENDPOINTCONFIG_101**: configurazione di tappping: url malformato
* **ERR_ENDPOINTCONFIG_102**: configurazione di tappping: url non valido: carattere jolly nell&#39;url non consentito in host:port
* **ERR_ENDPOINTCONFIG_103**: configurazione di tappping: metodi HTTP mancanti
* **ERR_ENDPOINTCONFIG_104**: configurazione di tappping: nessuna classificazione di chiamata definita
* **ERR_ENDPOINTCONFIG_107**: configurazione di tappping: conteggio massimo chiamate non valido (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: configurazione di tappping: conteggio massimo chiamate non valido (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: configurazione di tappping: impossibile creare la configurazione dell&#39;endpoint: payload non valido
* **ERR_ENDPOINTCONFIG_112**: configurazione di tappping: impossibile creare la configurazione dell&#39;endpoint: attesa di un payload JSON
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nome di servizio non valido `<!--<given value>-->`: deve essere &#39;dataSource&#39; o &#39;action&#39;

L&#39;avviso potenziale è:

**ERR_ENDPOINTCONFIG_106**: configurazione di tappping: connessioni HTTP massime non definite: nessuna limitazione per impostazione predefinita

## Casi d’uso

In questa sezione sono disponibili i cinque casi d’uso principali che è possibile eseguire per gestire la configurazione dei limiti in [!DNL Journey Orchestration].

Per facilitare i test e la configurazione, è disponibile una raccolta Postman [qui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Questa raccolta Postman è stata configurata per condividere la raccolta di variabili Postman generata tramite __[Integrazioni della console Adobe I/O](https://console.adobe.io/integrations) > Prova > Scarica per Postman__, che genera un file di ambiente Postman con i valori di integrazioni selezionati.

Una volta scaricata e caricata in Postman, devi aggiungere tre variabili: `{JO_HOST}`,`{BASE_PATH}` e `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] URL gateway
* `{BASE_PATH}` : punto di ingresso per l’API. Il valore è &#39;/authoring&#39;
* `{SANDBOX_NAME}` : intestazione **x-sandbox-name** (ad esempio, &quot;prod&quot;) corrispondente al nome della sandbox in cui avranno luogo le operazioni API. Consulta la sezione [panoramica sulle sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it) per ulteriori informazioni.

Nella sezione seguente, trovi l’elenco delle chiamate API rimanenti ordinate per eseguire il caso d’uso.

Caso d’uso n° 1: **Creazione e distribuzione di una nuova configurazione di tappatura**

1. list
1. creare
1. canonizzare
1. distribuire

Caso d’uso n° 2: **Aggiornare e distribuire una configurazione di limite non ancora distribuita**

1. list
1. get
1. update
1. canonizzare
1. distribuire

Caso d’uso n° 3: **Disdistribuire ed eliminare una configurazione di limitazione distribuita**

1. list
1. non distribuire
1. delete

Caso d’uso n° 4: **Elimina una configurazione di limitazione distribuita.**

In una sola chiamata API, puoi annullare la distribuzione ed eliminare la configurazione utilizzando il parametro forceDelete .
1. list
1. elimina, con param forceDelete

Caso d’uso n° 5: **Aggiornare una configurazione di limite già distribuita**

1. list
1. get
1. update
1. non distribuire
1. canonizzare
1. distribuire
