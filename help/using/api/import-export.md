---
product: adobe campaign
solution: Journey Orchestration
title: Importa descrizione API esportazione
description: Ulteriori informazioni sull'API di esportazione di importazione.
products: journeys
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 2%

---


# Utilizzo dell’API Export Import

Esporta una versione del percorso e tutti i relativi oggetti correlati (percorso, eventi, origini dati, gruppi di campi, azioni personalizzate) con una singola chiamata API. Il payload risultante dall’esportazione può essere utilizzato per importare facilmente il percorso in un altro ambiente (istanza o sandbox).
Questa funzione consente di gestire i viaggi in più istanze o per più flussi di lavoro in ambienti di test.


## Resources

L&#39;API di esportazione importazione Journey Orchestration è descritta in un file Swagger disponibile [qui](https://adobedocs.github.io/JourneyAPI/docs/).

Per utilizzare questa API con l&#39;istanza di Journey Orchestration, è necessario utilizzare la console AdobeI/O. Per iniziare, segui questa [Guida introduttiva  Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) per sviluppatori di Adobi e utilizza le sezioni presenti in questa pagina.

Per verificare e preparare l&#39;integrazione, è disponibile [qui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)una raccolta Postman.


## Flusso di esportazione-importazione

Per esportare e importare i vostri viaggi in diversi ambienti, si consiglia di seguire i seguenti passaggi:

1. Creare e impostare parametri per un viaggio nell’ambiente di partenza. [Maggiori informazioni qui](https://docs.adobe.com/content/help/it-IT/journeys/using/building-journeys/about-journey-building/journey.html)
1. Verificate che la versione del viaggio non contenga errori. [Maggiori informazioni qui](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. Chiama l’API **/list/trip** per recuperare il percorso UID e l’UID dell’ultima versione del viaggio. Se necessario, puoi chiamare **/viaggi/`{uid}`/ultimi** per trovare l’UID dell’ultima versione del viaggio.
1. Chiama l&#39;API **export** con i parametri dell&#39;ambiente di partenza (orgID e sandboxName).
1. Aprite il payload restituito, quindi verificate i seguenti elementi:
   * Se il viaggio esportato contiene credenziali **** specifiche, è necessario sostituire tali credenziali con quelle corrispondenti al nuovo ambiente.
   * Se il percorso esportato contiene **eventi** che puntano a uno schema **** XDM, è necessario aggiornare manualmente il riferimento dell&#39;ID dello schema con l&#39;ID dello schema del nuovo ambiente nel nodo xdmEntity, se i valori ID sono diversi. Questo aggiornamento deve essere fatto per ogni evento. [Maggiori informazioni qui](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * Se il viaggio contiene azioni e-mail, sms o push, potrebbe essere necessario aggiornare il nome del modello o il nome dell’app mobile se il nome nell’ambiente di destinazione è diverso da quello nell’ambiente di partenza.
1. Chiama l&#39;API **import** con l&#39;ambiente di destinazione. Potete richiamare l&#39;API di importazione il numero di volte desiderato. L’UUID e il nome di ciascun nodo contenuto nel percorso vengono generati ogni volta che chiamate l’API di importazione.
1. Una volta importato il viaggio, potete pubblicarlo nella nuova sandbox o nel nuovo ambiente.


## Autenticazione

### Impostazione dell’accesso API

L&#39;accesso API di Journey Orchestration è configurato attraverso i passaggi indicati di seguito. Ciascuno di questi passaggi è descritto nel [della documentazione](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)I/O del Adobe.

>[!CAUTION]
>
>Per gestire i certificati in  I/O Adobe, accertatevi di disporre dei diritti di amministratore <b>di</b> sistema sull&#39;organizzazione o su un account [](https://helpx.adobe.com/enterprise/using/manage-developers.html) sviluppatore nell&#39;Admin Console.

1. **Verificate di disporre di un certificato** digitale oppure createne uno, se necessario. Le chiavi pubblica e privata fornite con il certificato sono necessarie nei seguenti passaggi.
1. **Crea una nuova integrazione nel [!DNL Journey Orchestration] servizio** in  Adobe I/O e configurala. L&#39;accesso al profilo di prodotto è necessario per Journey Orchestration e Adobe Experience Platform. Le credenziali verranno quindi generate (Chiave API, Segreto cliente...).
1. **Create un token Web JSON (JWT)** dalle credenziali generate in precedenza e firmatelo con la vostra chiave privata. Il JWT codifica tutte le informazioni di identità e sicurezza necessarie per  Adobe per verificare la propria identità e concedere l&#39;accesso all&#39;API. Questo passaggio è dettagliato in questa [sezione](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Scambiate il JWT per ottenere un token** di accesso tramite una richiesta di POST o tramite l&#39;interfaccia della console per sviluppatori. Questo token di accesso dovrà essere utilizzato in ogni intestazione delle richieste API.

Per stabilire una sessione dell&#39;API I/O di Adobe  servizio sicuro, ogni richiesta a un servizio di Adobe  deve includere nell&#39;intestazione Autorizzazione le informazioni riportate di seguito.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZZAZIONE>**: Si tratta dell’ID organizzazione personale, un ID organizzazione viene fornito dal Adobe  per ogni istanza:

   * &lt;ORGANIZZAZIONE> : l&#39;istanza di produzione
   Per ottenere il valore ID ORGANIZZAZIONE, rivolgiti all’amministratore o al contatto tecnico  Adobe. È inoltre possibile recuperarlo  Adobe I/O quando si crea una nuova integrazione, nell&#39;elenco delle licenze (vedere la documentazione [I/O](https://www.adobe.io/authentication.html)Adobe).

* **&lt;ACCESS_TOKEN>**: Token di accesso personale, che è stato recuperato durante lo scambio del JWT tramite una richiesta di POST.

* **&lt;API_KEY>**: la chiave API personale. Viene fornito in  I/O Adobe dopo la creazione di una nuova integrazione in [!DNL Journey Orchestration] Service.



## Descrizione dell&#39;API Export Import

Questa API consente di esportare una versione del percorso e tutti gli oggetti correlati (percorso, eventi, origini dati, gruppi di campi, azioni personalizzate) in base al relativo uid.
Il payload risultante può essere utilizzato per importare la versione del percorso in un altro ambiente (sandbox o instance).

| Metodo | Percorso | Descrizione |
|---|---|---|
| `[POST]` | /pathVersions/import | Importare una versione del viaggio risultante da un’esportazione della versione del viaggio |
| `[GET]` | /pathVersions/`{uid}`/export | Esportare una versione di viaggio |
| `[GET]` | /viaggi/`{uid}`/ultimi | Ottieni l’ultima versione del viaggio per un viaggio |
| `[POST]` | /list/viaggi | Elenca i metadati dei viaggi e le versioni dei percorsi |


### Caratteristiche di esportazione e guardrail

* Le credenziali non vengono esportate e viene inserito un segnaposto (ad es. INSERT_SECRET_HERE).
Dopo l&#39;esportazione del payload, è necessario inserire manualmente le nuove credenziali (corrispondenti all&#39;ambiente di destinazione) prima di importare il payload nell&#39;ambiente di destinazione.

* Se l&#39;origine dati contiene il parametro **buildIn:true**, non è necessario sostituire &quot;INSERT_SECRET_HERE&quot;. Si tratta di un&#39;origine dati di sistema gestita automaticamente dall&#39;ambiente di viaggio.

* I seguenti oggetti vengono esportati ma non verranno mai importati nell&#39;ambiente di destinazione:
   * **DataProvider**:  acsDataProvider e acppsDataProvider
   * **Gruppi** di campi: acppsFieldGroup
   * **Azioni** personalizzate: acsAction

* Il percorso deve essere valido prima dell&#39;esportazione.

### Caratteristiche di importazione

* Durante l&#39;importazione, gli oggetti viaggio vengono creati con un nuovo UUID e un nuovo nome per garantire l&#39;univocità nell&#39;ambiente di destinazione (istanza o sandbox).

* Se il payload di importazione contiene segnaposto segreti, viene generato un errore. Prima della chiamata POST per importare il percorso, è necessario sostituire le informazioni sulle credenziali.

## Avvisi ed errori

Gli errori potenziali sono:

* Al momento **dell&#39;** esportazione, se la versione del viaggio non è valida: error 500

* Al momento **dell&#39;** importazione, se il payload non è valido dopo le modifiche o se le credenziali non sono definite correttamente nel payload: error 400

* Dopo il passaggio di importazione, se si tenta di pubblicare il percorso nell&#39;ambiente di destinazione senza modificare l&#39;ID dello schema XDM per gli eventi, viene visualizzato un errore.

