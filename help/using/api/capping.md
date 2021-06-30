---
product: adobe campaign
title: Limitazione della descrizione API
description: Ulteriori informazioni sull’API di limitazione di utilizzo.
products: journeys
feature: Percorsi
role: Business Practitioner
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: e42ef98b1d84d8311cf49967ec75ec9be6cc53f1
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 1%

---

# Utilizzo dell’API di limitazione utilizzo

## Introduzione

[!DNL Journey Orchestration]Le API di supportano eventi 5000/secondi, ma alcuni sistemi o API esterni non potrebbero avere una velocità effettiva equivalente. Ecco perché [!DNL Journey Orchestration] viene fornito con una funzione dedicata denominata API di limitazione per monitorare e limitare il tasso che imponiamo ai sistemi esterni.

Durante la configurazione di un’origine dati, definirai una connessione a un sistema per recuperare informazioni aggiuntive che verranno utilizzate nei percorsi oppure, per una definizione di azione, configurerai la connessione di un sistema di terze parti per l’invio di messaggi o chiamate API. Ogni volta che una chiamata API viene eseguita dal Percorso, l’API di limitazione viene interrogata, la chiamata viene eseguita tramite il motore API. Se è definito un limite, la chiamata viene rifiutata e il sistema esterno non verrà sovraccaricato.

Per le origini dati esterne, il numero massimo di chiamate al secondo è impostato su 15. Se il numero di chiamate supera il 15 al secondo, le chiamate rimanenti vengono scartate. Puoi aumentare questo limite per le origini dati esterne private. Contatta l’Adobe per inserire in una whitelist l’endpoint. Ciò non è possibile per le fonti di dati esterne pubbliche. Per ulteriori informazioni sulle best practice e sulle protezioni durante l&#39;integrazione di sistemi esterni, consulta questa [pagina](../about/external-systems.md).

Per ulteriori informazioni sulle azioni o sulla configurazione dell&#39;origine dati, consulta [Informazioni sulle azioni](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/action.html) o [Informazioni sulle origini dati](https://experienceleague.adobe.com/docs/journeys/using/data-source-journeys/about-data-sources.html)

## Resources

>[!NOTE]
>
>L’ [!DNL Journey Orchestration] API di limitazione di utilizzo è descritta all’interno di un file Swagger disponibile [qui](https://adobedocs.github.io/JourneyAPI/docs/).

Per utilizzare questa API con l’istanza [!DNL Journey Orchestration], è necessario utilizzare la console AdobeI/O. Per iniziare, segui la [Guida introduttiva ad Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) e utilizza le sezioni presenti in questa pagina.

Per testare e preparare l&#39;integrazione, è disponibile una raccolta Postman [qui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Autenticazione

### Impostazione dell’accesso alle API

[!DNL Journey Orchestration] L’accesso alle API è configurato attraverso i passaggi seguenti. Ognuno di questi passaggi è descritto nella [documentazione di Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Per gestire i certificati in Adobe I/O, assicurati di disporre dei diritti di <b>amministratore di sistema</b> sull’organizzazione o di un [account sviluppatore](https://helpx.adobe.com/enterprise/using/manage-developers.html) in Admin Console.

1. **Verifica di disporre di un certificato** digitale o creane uno, se necessario. Le chiavi pubbliche e private fornite con il certificato sono necessarie nei passaggi seguenti.
1. **Crea una nuova integrazione a  [!DNL Journey Orchestration]** Servicein Adobe I/O e configurala. L’accesso al profilo di prodotto è necessario per [!DNL Journey Orchestration] e Adobe Experience Platform. Le credenziali verranno quindi generate (chiave API, segreto client...).
1. **Crea un JSON Web Token (JWT)** dalle credenziali generate in precedenza e firmalo con la tua chiave privata. JWT codifica tutte le informazioni di identità e sicurezza necessarie per Adobe per verificare la tua identità e concedere l’accesso all’API. Questo passaggio è descritto in questa sezione [sezione](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Scambio di JWT per un** token di accesso tramite una richiesta POST o tramite l’interfaccia Console per sviluppatori. Questo token di accesso dovrà essere utilizzato in ogni intestazione delle richieste API.

Per stabilire una sessione API di Adobe I/O servizio-servizio sicura, ogni richiesta a un servizio Adobe deve includere nell’intestazione Autorizzazione le informazioni riportate di seguito.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Si tratta dell’ID organizzazione personale, un ID organizzazione viene fornito per Adobe per ciascuna istanza :

   * &lt;organization> : l&#39;istanza di produzione

   Per ottenere il valore dell’ID ORGANIZZAZIONE, rivolgiti all’amministratore o al contatto tecnico Adobe. Puoi anche recuperarlo in Adobe I/O durante la creazione di una nuova integrazione, nell&#39;elenco delle licenze (consulta la <a href="https://www.adobe.io/authentication.html">documentazione di Adobe I/O</a>).

* **&lt;access_token>**: Token di accesso personale, recuperato durante lo scambio di JWT tramite una richiesta POST.

* **&lt;api_key>**: la tua chiave API personale. Viene fornito in Adobe I/O dopo la creazione di una nuova integrazione al servizio [!DNL Journey Orchestration] .



## Limitazione della descrizione API

L’API di limitazione di utilizzo consente di creare, configurare e monitorare le configurazioni di limitazione di utilizzo.

| Elemento “method” | Percorso | Descrizione |
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

Quando viene chiamato un metodo **canDeploy**, il processo convalida la configurazione e restituisce lo stato di convalida identificato dal relativo ID univoco, ovvero:

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
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: nome di servizio non valido  `<!--<given value>-->`: deve essere &#39;dataSource&#39; o &#39;action&#39;


L&#39;avviso potenziale è:

**ERR_ENDPOINTCONFIG_106**: configurazione di tappping: connessioni HTTP massime non definite: nessuna limitazione per impostazione predefinita



## Casi d’uso

In questa sezione sono disponibili i cinque casi d’uso principali che è possibile eseguire per gestire la configurazione dei limiti in [!DNL Journey Orchestration].

Per facilitare i test e la configurazione, è disponibile una raccolta Postman [qui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Questa raccolta Postman è stata impostata per condividere la raccolta Postman Variable generata tramite __[Integrazioni della console Adobe I/O](https://console.adobe.io/integrations) > Prova > Scarica per Postman__, che genera un file Postman Environment con i valori di integrazioni selezionati.

Una volta scaricata e caricata in Postman, devi aggiungere tre variabili: `{JO_HOST}`,`{Base_Path}` e `{SANDBOX_NAME}`.
* `{JO_HOST}` :  [!DNL Journey Orchestration] URL gateway
* `{BASE_PATH}` : punto di ingresso per l’API. Il valore è &#39;/authoring&#39;
* `{SANDBOX_NAME}` : l’intestazione  **x-sandbox-name**  (ad esempio, &quot;prod&quot;) corrispondente al nome della sandbox in cui avranno luogo le operazioni API. Per ulteriori informazioni, consulta la [panoramica sulle sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) .

Nella sezione seguente, trovi l’elenco delle chiamate API rimanenti ordinate per eseguire il caso d’uso.

Caso d’uso n° 1: **Creazione e distribuzione di una nuova configurazione di limitazione**

1. elenco
1. creare
1. canonizzare
1. distribuire

Caso d’uso n° 2: **Aggiornare e distribuire una configurazione di limite non ancora distribuita**

1. elenco
1. get
1. update
1. canonizzare
1. distribuire

Caso d’uso n° 3: **Disimplementare ed eliminare una configurazione di limite distribuita**

1. elenco
1. non distribuire
1. delete

Caso d’uso n° 4: **Eliminare una configurazione di limitazione distribuita.**

In una sola chiamata API, puoi annullare la distribuzione ed eliminare la configurazione utilizzando il parametro forceDelete .
1. elenco
1. elimina, con param forceDelete

Caso d’uso n° 5: **Aggiornare una configurazione di limite già distribuita**

1. elenco
1. get
1. update
1. non distribuire
1. canonizzare
1. distribuire
