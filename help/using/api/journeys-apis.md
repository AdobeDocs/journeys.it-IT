---
product: adobe campaign
title: Guida introduttiva alle API di percorsi
description: Ulteriori informazioni sulle API dei percorsi
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: 137637a753ba44cc4f8e397b77c3fc076ec3de3f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 2%

---

# Guida introduttiva alle API di percorsi

## Informazioni sulle API di limitazione e limitazione

Durante la configurazione di un’origine dati o di un’azione, stabilisci una connessione a un sistema per recuperare informazioni aggiuntive da utilizzare nei percorsi oppure per inviare messaggi o chiamate API.

Le API dei percorsi supportano fino a 5000 eventi al secondo, ma alcuni sistemi o API esterni potrebbero non avere una velocità effettiva equivalente. Per evitare il sovraccarico di questi sistemi, puoi utilizzare il **Limitazione** e **Limitazione** API per limitare il numero di eventi inviati al secondo.

Ogni volta che una chiamata API viene eseguita dai percorsi, passa attraverso il motore API. Se viene raggiunto il limite impostato nell’API, la chiamata viene rifiutata se utilizzi l’API di limitazione delle funzioni o viene messa in coda ed elaborata il prima possibile nell’ordine in cui sono state ricevute se utilizzi l’API di limitazione delle prestazioni.

Ad esempio, supponiamo che tu abbia definito una regola di limitazione o limitazione di 100 chiamate al secondo per il sistema esterno. Il sistema viene chiamato da un&#39;azione personalizzata in 10 percorsi diversi. Se un percorso riceve 200 chiamate al secondo, utilizza i 100 slot disponibili ed elimina o mette in coda i 100 slot rimanenti. Poiché la tariffa massima è stata superata, gli altri 9 percorsi non avranno più alcuna slot. Questa granularità aiuta a proteggere il sistema esterno da sovraccarichi e crash.

>[!IMPORTANT]
>
>**Regole di limitazione** sono configurati a livello di sandbox, per un endpoint specifico (l’URL chiamato) ma sono globali per tutti i percorsi di tale sandbox.
>
>**Regole di limitazione** sono configurati solo sulle sandbox di produzione, per un endpoint specifico ma globale per tutti i percorsi in tutte le sandbox. Puoi disporre di una sola configurazione di limitazione per organizzazione.

Per ulteriori informazioni su come utilizzare queste API, consulta queste sezioni:

* [API di limitazione](capping.md)
* [API di limitazione](throttling.md)

Entrambe le API sono descritte anche in un file Swagger disponibile [qui](https://adobedocs.github.io/JourneyAPI/docs/).

## Origini dati e capacità di azioni personalizzate {#capacity}

Per **origini dati esterne**, il numero massimo di chiamate al secondo è limitato a 15. Se questo limite viene superato, tutte le chiamate aggiuntive vengono scartate o messe in coda a seconda dell’API in uso. È possibile aumentare questo limite per le origini dati esterne private contattando Adobe per includere l’endpoint nell’inserire nell&#39;elenco Consentiti, ma questa non è un’opzione per le origini dati esterne pubbliche. * [Scopri come configurare le origini dati](../datasource/about-data-sources.md).

>[!NOTE]
>
>Se un’origine dati utilizza un’autenticazione personalizzata con un endpoint diverso da quello utilizzato per l’origine dati, è necessario contattare Adobe per includere tale endpoint nell’inserire nell&#39;elenco Consentiti.

Per **azioni personalizzate**, devi valutare la capacità dell’API esterna. Ad esempio, se Journey Optimizer invia 1000 chiamate al secondo e il sistema supporta solo 100 chiamate al secondo, è necessario definire una configurazione di limitazione o limitazione in modo che il sistema non saturi. [Scopri come configurare le azioni](../action/action.md)

## Impostazione dell’accesso alle API {#api}

Per utilizzare queste API con le [!DNL Journey Orchestration] ad esempio, è necessario utilizzare la console AdobeI/O. [!DNL Journey Orchestration] L’accesso alle API è configurato attraverso i passaggi seguenti. Ciascuno di questi passaggi è descritto nella sezione [Documentazione di Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Per gestire i certificati in Adobe I/O, assicurati di disporre di <b>Amministratore di sistema</b> diritti dell&#39;organizzazione o [account sviluppatore](https://helpx.adobe.com/it/enterprise/using/manage-developers.html) in Admin Console.

1. **Verifica di disporre di un certificato digitale** oppure creane uno, se necessario. Le chiavi pubbliche e private fornite con il certificato sono necessarie nei passaggi seguenti.
1. **Creare una nuova integrazione in [!DNL Journey Orchestration] Servizio** in Adobe I/O e configuralo. L’accesso al profilo di prodotto è necessario per [!DNL Journey Orchestration] e Adobe Experience Platform. Le credenziali verranno quindi generate (chiave API, segreto client...).
1. **Creare un token web JSON (JWT)** dalle credenziali generate in precedenza e firmalo con la tua chiave privata. JWT codifica tutte le informazioni di identità e sicurezza necessarie per Adobe per verificare la tua identità e concedere l’accesso all’API. Questo passaggio è descritto in [sezione](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Sostituire il JWT con un token di accesso** tramite una richiesta POST o tramite l’interfaccia Console per sviluppatori. Questo token di accesso dovrà essere utilizzato in ogni intestazione delle richieste API.

Per stabilire una sessione API di Adobe I/O servizio-servizio sicura, ogni richiesta a un servizio Adobe deve includere nell’intestazione Autorizzazione le informazioni riportate di seguito.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Si tratta dell’ID organizzazione personale, un ID organizzazione viene fornito per Adobe per ciascuna istanza. Per ottenere il valore dell’ID ORGANIZZAZIONE, rivolgiti all’amministratore o al contatto tecnico Adobe. È inoltre possibile recuperarlo in Adobe I/O durante la creazione di una nuova integrazione, nell&#39;elenco delle licenze (consulta <a href="https://www.adobe.io/authentication.html">Documentazione di Adobe I/O</a>).

* **&lt;access_token>**: Token di accesso personale, recuperato durante lo scambio di JWT tramite una richiesta POST.

* **&lt;api_key>**: la tua chiave API personale. Viene fornito in Adobe I/O dopo la creazione di una nuova integrazione in [!DNL Journey Orchestration] Servizio.
