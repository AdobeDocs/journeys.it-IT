---
product: adobe campaign
title: Introduzione alle API dei percorsi
description: Ulteriori informazioni sulle API dei percorsi
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
source-git-commit: 8f409fe6e37a3b80527d9a5514b066e539dcd9f3
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 89%

---

# Introduzione alle API dei percorsi

## Informazioni sulle API di limitazione di utilizzo e di limitazione

Durante la configurazione di un’origine dati o di un’azione, viene stabilita una connessione a un sistema per recuperare informazioni aggiuntive da utilizzare nei percorsi oppure per inviare messaggi o chiamate API.

Le API dei percorsi supportano fino a 5000 eventi al secondo, ma alcuni sistemi o API esterni potrebbero non avere una velocità effettiva equivalente. Per evitare il sovraccarico di questi sistemi, è possibile utilizzare le API di **Limitazione di utilizzo** e di **Limitazione** per limitare il numero di eventi inviati al secondo.

Ogni volta che una chiamata API viene eseguita dai percorsi, passa attraverso il motore API. Se il limite impostato nell’API viene raggiunto, la chiamata viene rifiutata se utilizzi l’API di limitazione di utilizzo, oppure viene messa in coda per un massimo di 6 ore ed elaborata il prima possibile nell’ordine in cui è stata ricevuta se utilizzi l’API di limitazione.

Ad esempio, supponiamo che tu abbia definito una regola di limitazione o limitazione di 100 chiamate al secondo per il sistema esterno. Il sistema viene chiamato da un’azione personalizzata in 10 percorsi diversi. Se un percorso riceve 200 chiamate al secondo, utilizza i 100 slot disponibili ed elimina o mette in coda i 100 slot rimanenti. Poiché il limite massimo è stato superato, gli altri 9 percorsi non avranno più alcuno slot. Questa granularità aiuta a proteggere il sistema esterno da sovraccarichi e arresti anomali.

>[!IMPORTANT]
>
>Le **regole di limitazione di utilizzo** sono configurate a livello di sandbox, per un endpoint specifico (l’URL chiamato) ma sono globali per tutti i percorsi di tale sandbox.
>
>Le **regole di limitazione** sono configurate solo sulle sandbox di produzione, per un endpoint specifico ma globale per tutti i percorsi in tutte le sandbox. Si può disporre di una sola configurazione di limitazione per organizzazione.

Per ulteriori informazioni su come utilizzare queste API, consulta queste sezioni:

* [API di limitazione di utilizzo](capping.md)
* [API di limitazione](throttling.md)

Entrambe le API sono descritte anche in un file Swagger disponibile [qui](https://adobedocs.github.io/JourneyAPI/docs/).

## Origini dati e capacità di azioni personalizzate {#capacity}

Per le **origini dati esterne**, il numero massimo di chiamate al secondo è limitato a 15. Se questo limite viene superato, tutte le chiamate aggiuntive vengono scartate o messe in coda a seconda dell’API in uso. È possibile aumentare questo limite per le origini dati esterne private contattando Adobe per includere l’endpoint nell&#39;elenco Consentiti, ma questa non è un’opzione per le origini dati esterne pubbliche. * [Informazioni su come configurare le origini dati esterne](../datasource/about-data-sources.md).

>[!NOTE]
>
>Se un’origine dati utilizza un’autenticazione personalizzata con un endpoint diverso da quello utilizzato per l’origine dati, è necessario contattare Adobe per includere tale endpoint nell’elenco Consentiti.

Per le **azioni personalizzate**, è necessario valutare la capacità dell’API esterna. Ad esempio, se Journey Optimizer invia 1000 chiamate al secondo e il sistema supporta solo 100 chiamate al secondo, è necessario definire una configurazione di limitazione di utilizzo o di limitazione in modo che il sistema non si saturi. [Informazioni su come configurare le azioni](../action/action.md)

## Configurazione dell’accesso alle API {#api}

Per utilizzare queste API con l’istanza di [!DNL Journey Orchestration], è necessario utilizzare la console Adobe I/O. L’accesso alle API di [!DNL Journey Orchestration] è configurato attraverso la procedura indicata di seguito. Ogni passaggio è descritto in dettaglio nella [Documentazione di Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Per gestire i certificati in Adobe I/O, assicurati di disporre di diritti di <b>Amministratore di sistema</b> dell&#39;organizzazione o di un [account sviluppatore](https://helpx.adobe.com/it/enterprise/using/manage-developers.html) in Admin Console.

1. **Verifica di disporre di un certificato digitale** oppure creane uno, se necessario. Le chiavi pubbliche e private fornite con il certificato sono necessarie nei passaggi seguenti.
1. **Crea una nuova integrazione al servizio [!DNL Journey Orchestration]** in Adobe I/O e configuralo. L’accesso al profilo di prodotto è necessario per [!DNL Journey Orchestration] e Adobe Experience Platform. Quindi saranno generate le credenziali (chiave API, segreto client...).

>[!CAUTION]
>
>Il metodo JWT per generare i token di accesso è stato dichiarato obsoleto. Tutte le nuove integrazioni devono essere create utilizzando [Metodo di autenticazione server-to-server OAuth](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server). Adobe consiglia inoltre di migrare le integrazioni esistenti al metodo OAuth.
>
>Leggi le seguenti importanti documentazioni:
>[Guida alla migrazione per le applicazioni da JWT a OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/),
>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/),
>[Vantaggi dell’utilizzo del metodo di credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)

Per stabilire una sessione API di Adobe I/O servizio-servizio sicura, ogni richiesta a un servizio di Adobe deve includere nell’intestazione dell’autorizzazione le informazioni riportate di seguito.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: si tratta dell’ID organizzazione personale, un ID organizzazione viene fornito da Adobe per ciascuna istanza. Per ottenere il valore dell’ID organizzazione, rivolgiti all’amministratore o al contatto tecnico Adobe. È inoltre possibile recuperarlo in Adobe I/O durante la creazione di una nuova integrazione, nell’elenco delle licenze (consulta la <a href="https://www.adobe.io/authentication.html">documentazione di Adobe I/O</a>).

* **&lt;access_token>**: token di accesso personale

* **&lt;API_KEY>**: la tua chiave API personale. Viene fornita in Adobe I/O dopo la creazione di una nuova integrazione nel servizio [!DNL Journey Orchestration].
