---
product: adobe campaign
title: Descrizione API di limitazione
description: Scopri di più sull’API di limitazione di utilizzo.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 27%

---


# Utilizzare l’API di limitazione di utilizzo {#work}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


L’API di limitazione di utilizzo consente di creare, configurare e monitorare le configurazioni di limitazione di utilizzo.

## Descrizione API di limitazione

| Metodo | Percorso | Descrizione |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Ottieni un elenco delle configurazioni del limite dell’endpoint |
| [!DNL POST] | /endpointConfigs | Creare una configurazione di limitazione di endpoint |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | Distribuire una configurazione di limitazione di endpoint |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | Annullare la distribuzione di una configurazione di limitazione di endpoint |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | Controlla se è possibile distribuire o meno una configurazione di limitazione di endpoint |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Aggiornare la configurazione della limitazione di un endpoint |
| [!DNL GET] | /endpointConfigs/`{uid}` | Recuperare la configurazione della limitazione di un endpoint |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Eliminare una configurazione di limitazione degli endpoint |

Quando viene creata o aggiornata una configurazione, viene eseguito automaticamente un controllo per garantire la sintassi e l’integrità del payload.
Se si verificano alcuni problemi, l’operazione restituisce un avviso o degli errori per facilitare la correzione della configurazione.

## Configurazione endpoint

Di seguito è riportata la struttura di base di una configurazione di endpoint:

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint (optional)>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

>[!IMPORTANT]
>
>Il parametro **maxHttpConnections** è facoltativo. Consente di limitare il numero di connessioni aperte da Journey Optimizer al sistema esterno.
>
>Il valore massimo impostabile è 400. Se non viene specificato nulla, il sistema può aprire più di migliaia di connessioni a seconda della scalabilità dinamica del sistema.

### Esempio:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 50,
      "rating": {
        "maxCallsCount": 500,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## Avvertenze ed errori

Quando viene chiamato un metodo **canDeploy**, il processo convalida la configurazione e restituisce lo stato di convalida identificato dal relativo ID univoco:

```
"ok" or "error"
```

I potenziali errori sono:

* **ERR_ENDPOINTCONFIG_100**: configurazione limite: URL mancante o non valido
* **ERR_ENDPOINTCONFIG_101**: configurazione limite: URL non valido
* **ERR_ENDPOINTCONFIG_102**: configurazione limite: URL non valido: wildchar nell&#39;URL non consentito in host:porta
* **ERR_ENDPOINTCONFIG_103**: configurazione limite: metodi HTTP mancanti
* **ERR_ENDPOINTCONFIG_104**: configurazione limite: nessuna classificazione di chiamata definita
* **ERR_ENDPOINTCONFIG_107**: configurazione limite: numero massimo di chiamate non valido (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: configurazione limite: numero massimo di chiamate non valido (periodInMs)
* **ERR_ENDPOINTCONFIG_111**: configurazione limite: impossibile creare la configurazione endpoint: payload non valido
* **ERR_ENDPOINTCONFIG_112**: configurazione limite: impossibile creare la configurazione dell&#39;endpoint: previsto un payload JSON
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nome di servizio `<!--<given value>-->` non valido: deve essere &#39;dataSource&#39; o &#39;action&#39;

Il potenziale avviso è:

**ERR_ENDPOINTCONFIG_106**: configurazione limite: numero massimo di connessioni HTTP non definite: nessuna limitazione per impostazione predefinita

## Casi d’uso

In questa sezione troverai i cinque casi d&#39;uso principali che puoi eseguire per gestire la configurazione dei limiti in [!DNL Journey Orchestration].

Per facilitare i test e la configurazione, [qui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json) è disponibile una raccolta Postman.

Questa raccolta Postman è stata configurata per condividere la raccolta di variabili Postman generata tramite __[Integrazioni della console di Adobe I/O](https://console.adobe.io/integrations) > Prova > Scarica per Postman__, che genera un file di ambiente Postman con i valori delle integrazioni selezionate.

Una volta scaricata e caricata in Postman, è necessario aggiungere tre variabili: `{JO_HOST}`,`{BASE_PATH}` e `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] URL gateway
* `{BASE_PATH}` : punto di ingresso per l’API. Il valore è “/authoring”
* `{SANDBOX_NAME}`: l’intestazione **x-sandbox-name** (ad esempio, “prod”) corrispondente al nome della sandbox in cui si svolgeranno le operazioni API. Per ulteriori informazioni, consulta la [panoramica delle sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it).

Nella sezione seguente, è disponibile un elenco ordinato delle chiamate API REST per eseguire il caso d’uso.

Caso d&#39;uso n. 1: **Creazione e distribuzione di una nuova configurazione di limite**

1. list
1. create
1. candeploy
1. deploy

Caso d&#39;uso n. 2: **Aggiornare e distribuire una configurazione di limite non ancora distribuita**

1. list
1. get
1. update
1. candeploy
1. deploy

Caso d&#39;uso n. 3: **Annullamento della distribuzione ed eliminazione di una configurazione di limitazione implementata**

1. list
1. undeploy
1. delete

Caso d&#39;uso n. 4: **Eliminare una configurazione di limitazione distribuita.**

È possibile annullare la distribuzione ed eliminare la configurazione in una sola chiamata API utilizzando il parametro forceDelete.
1. list
1. eliminare, con il parametro forceDelete

Caso d&#39;uso n. 5: **Aggiornamento di una configurazione di limite già distribuita**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
