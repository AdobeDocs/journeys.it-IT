---
product: adobe campaign
title: Utilizzare l’API di limitazione
description: Ulteriori informazioni sull’API di limitazione
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 76afe397-3e18-4e01-9b0b-c21705927ce2
source-git-commit: 25d8dcd027f3f433759ce97f9a3a1dad85ba1427
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 2%

---

# Utilizzare l’API di limitazione

L’API di limitazione consente di creare, configurare e monitorare le configurazioni di limitazione per limitare il numero di eventi inviati al secondo.

>[!IMPORTANT]
>
>È attualmente consentita una sola configurazione per organizzazione. Una configurazione deve essere definita su una sandbox di produzione (fornita tramite x-sandbox-name nelle intestazioni).
>
>Viene applicata una configurazione a livello di organizzazione.
>
>Al raggiungimento del limite impostato nell’API, altri eventi vengono messi in coda per un massimo di 6 ore. Impossibile modificare questo valore.

## Descrizione API di limitazione {#description}

| Metodo | Path | Descrizione |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | Ottieni un elenco delle configurazioni di limitazione |
| [!DNL POST] | /throttlingConfigs | Creare una configurazione di limitazione |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | Distribuzione di una configurazione di limitazione |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | Disdistribuire una configurazione di limitazione |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | Controlla se una configurazione di limitazione può essere implementata o meno |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Aggiornare una configurazione di limitazione |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Recuperare una configurazione di limitazione |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Eliminare una configurazione di limitazione |

## Configurazione della limitazione {#configuration}

Ecco la struttura di una configurazione di limitazione. **name** e **descrizione** gli attributi sono facoltativi.

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

Durante la creazione o l&#39;aggiornamento di una configurazione, il processo convalida la configurazione specificata e restituisce lo stato di convalida identificato dal relativo ID univoco:

```
"ok" or "error"
```

>[!IMPORTANT]
>
>Attributi **maxThroughput**, **urlPattern** e **Metodi** sono obbligatori.
>
>**maxThroughput** Il valore deve essere compreso nell&#39;intervallo 200-5000.

Durante la creazione, l’eliminazione o la distribuzione della configurazione di limitazione, possono verificarsi i seguenti errori:

* **ERR_THROTTLING_CONFIG_100**: configurazione di limitazione: `<mandatory attribute>` obbligatorio
* **ERR_THROTTLING_CONFIG_101**: configurazione di limitazione: maxThroughput è obbligatorio e deve essere maggiore o uguale a 200 e minore o uguale a 5000
* **ERR_THROTTLING_CONFIG_104**: configurazione di limitazione: modello url malformato
* **ERR_THROTTLING_CONFIG_105**: configurazione di limitazione: caratteri jolly non consentiti nella parte host del pattern url
* **ERR_THROTTLING_CONFIG_106**: configurazione di limitazione: payload non valido
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**, &quot;Impossibile eliminare una configurazione di limitazione distribuita. Disdistribuirlo prima di eliminarlo&quot;
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, &quot;Impossibile eliminare la configurazione di limitazione: si verifica un errore imprevisto&quot;
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, &quot;Impossibile distribuire la configurazione di limitazione: si verifica un errore imprevisto&quot;
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, &quot;Impossibile annullare la distribuzione della configurazione di limitazione: si verifica un errore imprevisto&quot;
* **THROTTLING_CONFIG_GET_ERROR: 1460**, &quot;Impossibile ottenere la configurazione di limitazione: si verifica un errore imprevisto&quot;
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, &quot;Impossibile aggiornare la configurazione di limitazione: la versione runtime non è attiva&quot;
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, &quot;Impossibile aggiornare la configurazione di limitazione: si verifica un errore imprevisto&quot;
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, &quot;Operazione non consentita nella configurazione di limitazione: sandbox non prod&quot;
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**, &quot;Impossibile creare la configurazione di limitazione: si verifica un errore imprevisto&quot;
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, &quot;Impossibile creare la configurazione di limitazione: una sola configurazione consentita per organizzazione&quot;
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**, &quot;Impossibile distribuire la configurazione di limitazione: già distribuito&quot;
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**, &quot;throttling config not found&quot;
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**, &quot;Impossibile annullare la distribuzione della configurazione di limitazione: non ancora distribuito&quot;

**Esempi di errori**

Quando si tenta di creare una configurazione su sandbox non prod:

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

Nel caso in cui una data casella di controllo non esista:

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

Quando si tenta di creare un&#39;altra configurazione:

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## Casi d’uso {#uc}

Per facilitare i test e la configurazione, è disponibile una raccolta Postman [qui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Throttling-API_postman-collection.json).

Questa raccolta Postman è stata configurata per condividere la raccolta di variabili Postman generata tramite __[Integrazioni della console Adobe I/O](https://console.adobe.io/integrations) > Prova > Scarica per Postman__, che genera un file di ambiente Postman con i valori di integrazioni selezionati.

Una volta scaricata e caricata in Postman, devi aggiungere tre variabili: `{JO_HOST}`,`{BASE_PATH}` e `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] URL gateway
* `{BASE_PATH}` : punto di ingresso per l’API. Il valore è &#39;/authoring&#39;
* `{SANDBOX_NAME}` : intestazione **x-sandbox-name** (ad esempio, &quot;prod&quot;) corrispondente al nome della sandbox in cui avranno luogo le operazioni API. Consulta la sezione [panoramica sulle sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=it) per ulteriori informazioni.

Nella sezione seguente, trovi l’elenco delle chiamate API rimanenti ordinate per eseguire il caso d’uso.

Caso d’uso n° 1: **Creazione e distribuzione di una nuova configurazione di limitazione**

1. list
1. creare
1. canonizzare
1. distribuire

Caso d’uso n° 2: **Aggiornare e distribuire una configurazione di limitazione non ancora distribuita**

1. list
1. get
1. update
1. canonizzare
1. distribuire

Caso d’uso n° 3: **Disdistribuire ed eliminare una configurazione di limitazione distribuita**

1. list
1. non distribuire
1. delete

Caso d’uso n° 4: **Eliminare una configurazione di limitazione implementata**

In una sola chiamata API, puoi annullare la distribuzione ed eliminare la configurazione utilizzando il parametro forceDelete .

1. list
1. elimina, con param forceDelete

Caso d’uso n° 5: **Aggiornare una configurazione di limitazione già distribuita**

>[!NOTE]
>
>Non è necessario annullare la distribuzione della configurazione prima dell’aggiornamento

1. list
1. get
1. update

## Ciclo di vita della configurazione a livello di runtime {#config}

Quando una configurazione non viene distribuita, viene contrassegnata come inattiva a livello di runtime e gli eventi in sospeso continuano a essere elaborati durante 24 ore. Viene quindi eliminato nel servizio runtime.

Una volta rimossa la distribuzione di una configurazione, è possibile aggiornarla e ridistribuirla. In questo modo verrà creata una nuova configurazione di runtime da considerare nell’esecuzione delle azioni successive.

Quando aggiorni una configurazione già distribuita, i nuovi valori vengono presi in considerazione immediatamente. Le risorse di sistema sottostanti vengono automaticamente adattate. Questa funzione è ottimale se non si esegue la distribuzione e quindi si ridistribuisce la configurazione.

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

**Leggi (dopo l&#39;aggiornamento) - GET**

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

**Leggi (dopo la distribuzione) - GET**

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
