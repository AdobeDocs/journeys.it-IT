---
product: adobe campaign
title: Utilizzare l’API di limitazione
description: Ulteriori informazioni sull’API di limitazione
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 76afe397-3e18-4e01-9b0b-c21705927ce2
source-git-commit: 7b8c9d2bfe244b040a9064a7a240ea6f43cc8b41
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 96%

---

# Utilizzare l’API di limitazione

L’API di limitazione ti consente di creare, configurare e monitorare le configurazioni di limitazione al fine di limitare il numero di eventi inviati al secondo.

>[!IMPORTANT]
>
>Attualmente è consentita una sola configurazione per organizzazione. Una configurazione deve essere definita su una sandbox di produzione (specificata tramite x-sandbox-name nelle intestazioni).
>
>Viene applicata una configurazione per livello di organizzazione.
>
>Al raggiungimento del limite impostato nell’API, gli altri eventi vengono messi in coda per un massimo di 6 ore. Impossibile modificare questo valore.

## Descrizione dell’API di limitazione {#description}

| Metodo | Percorso | Descrizione |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | Ottenere un elenco delle configurazioni di limitazione |
| [!DNL POST] | /throttlingConfigs | Creare una configurazione di limitazione |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | Distribuire una configurazione di limitazione |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | Annullare la distribuzione di una configurazione di limitazione |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | Verificare se una configurazione di limitazione può essere distribuita o meno |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Aggiornare una configurazione di limitazione |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Recuperare una configurazione di limitazione |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Eliminare una configurazione di limitazione |

## Configurazione di limitazione {#configuration}

Di seguito è riportata la struttura di una configurazione di limitazione. Gli attributi **name** e **description** sono facoltativi.

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

Esempio:

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

## Errori

Durante la creazione o l’aggiornamento di una configurazione, il processo convalida la configurazione specificata e restituisce lo stato di convalida identificato dal relativo ID univoco:

```
"ok" or "error"
```

>[!IMPORTANT]
>
>Gli attributi **maxThroughput**, **urlPattern** e **methods** sono obbligatori.
>
>Il valore **maxThroughput** deve essere compreso nell’intervallo 200-5000.

Durante la creazione, l’eliminazione o la distribuzione della configurazione di limitazione, possono verificarsi i seguenti errori:

* **ERR_THROTTLING_CONFIG_100**: configurazione di limitazione: `<mandatory attribute>` obbligatoria
* **ERR_THROTTLING_CONFIG_101**: configurazione di limitazione: maxThroughput è obbligatorio e deve essere maggiore o uguale a 200 e minore o uguale a 5000
* **ERR_THROTTLING_CONFIG_104**: configurazione di limitazione: formato del pattern URL non valido
* **ERR_THROTTLING_CONFIG_105**: configurazione di limitazione: caratteri jolly non consentiti nella parte dell’host del pattern URL
* **ERR_THROTTLING_CONFIG_106**: configurazione di limitazione: payload non valido
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**, “Impossibile eliminare una configurazione di limitazione distribuita. Annullare la distribuzione prima di eliminarla”
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, “Impossibile eliminare la configurazione di limitazione: si è verificato un errore imprevisto”
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, “Impossibile distribuire la configurazione di limitazione: si è verificato un errore imprevisto”
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, “Impossibile annullare la distribuzione della configurazione di limitazione: si è verificato un errore imprevisto”
* **THROTTLING_CONFIG_GET_ERROR: 1460**, “Impossibile ottenere la configurazione di limitazione: si è verificato un errore imprevisto”
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, “Impossibile aggiornare la configurazione di limitazione: la versione di runtime non è attiva”
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, “Impossibile aggiornare la configurazione di limitazione: si è verificato un errore imprevisto”
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, “Operazione non consentita nella configurazione di limitazione: sandbox non di produzione”
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**, “Impossibile creare la configurazione di limitazione: si è verificato un errore imprevisto”
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, “Impossibile creare la configurazione di limitazione: è consentita una sola configurazione per organizzazione”
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**, “Impossibile distribuire la configurazione di limitazione: è già stata distribuita”
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**, “Nessuna configurazione di limitazione trovata”
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**, “Impossibile annullare la distribuzione della configurazione di limitazione: non è ancora stata distribuita”

**Esempi di errori**

Quando si tenta di creare una configurazione su sandbox non di produzione:

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

Nel caso in cui la sandbox specificata non esiste:

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

Quando si tenta di creare un’altra configurazione:

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## Casi d’uso {#uc}

Per facilitare i test e la configurazione, [qui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Throttling-API_postman-collection.json) è disponibile una raccolta Postman.

Questa raccolta Postman è stata configurata per condividere la raccolta di variabili Postman generata tramite __[Integrazioni della console di Adobe I/O](https://console.adobe.io/integrations) > Prova > Scarica per Postman__, che genera un file di ambiente Postman con i valori delle integrazioni selezionate.

Una volta scaricata e caricata in Postman, è necessario aggiungere tre variabili: `{JO_HOST}`,`{BASE_PATH}` e `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] URL gateway
* `{BASE_PATH}` : punto di ingresso per l’API. Il valore è “/authoring”
* `{SANDBOX_NAME}`: l’intestazione **x-sandbox-name** (ad esempio, “prod”) corrispondente al nome della sandbox in cui si svolgeranno le operazioni API. Per ulteriori informazioni, consulta la [panoramica delle sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it).

Nella sezione seguente, è disponibile un elenco ordinato delle chiamate API REST per eseguire il caso d’uso.

Caso d’uso n°1: **Creazione e distribuzione di una nuova configurazione di limitazione**

1. list
1. create
1. candeploy
1. deploy

Caso d’uso n° 2: **Aggiornare e distribuire una configurazione di limitazione non ancora distribuita**

1. list
1. get
1. update
1. candeploy
1. deploy

Caso d’uso n° 3: **Annullare la distribuzione ed eliminare una configurazione di limitazione distribuita**

1. list
1. undeploy
1. delete

Caso d’uso n° 4: **Eliminare una configurazione di limitazione distribuita**

È possibile annullare la distribuzione ed eliminare la configurazione in una sola chiamata API utilizzando il parametro forceDelete.

1. list
1. eliminare, con il parametro forceDelete

Caso d’uso n° 5: **Aggiornare una configurazione di limitazione già distribuita**

>[!NOTE]
>
>Non è richiesto annullare la distribuzione della configurazione prima dell’aggiornamento

1. list
1. get
1. update

## Ciclo di vita della configurazione a livello di runtime {#config}

Quando la distribuzione di una configurazione viene annullata, questa viene contrassegnata come inattiva a livello di runtime e gli eventi in sospeso continuano a essere elaborati per 24 ore. Quindi viene eliminata nel servizio di runtime.

Una volta annullata la distribuzione di una configurazione, è possibile aggiornarla e ridistribuirla. In questo modo verrà creata una nuova configurazione di runtime che verrà considerata nell’esecuzione delle azioni successive.

Durante l’aggiornamento di una configurazione già distribuita, i nuovi valori vengono presi in considerazione immediatamente. Le risorse di sistema sottostanti vengono automaticamente adattate. Questa è una soluzione ottimale rispetto alla distribuzione e ridistribuzione della configurazione.

## Esempi di risposte {#responses}

**Creazione - POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**Aggiornamento - PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**Lettura (dopo l’aggiornamento) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**Lettura (dopo la distribuzione) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```
