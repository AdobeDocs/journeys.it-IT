---
product: adobe campaign
title: Importa descrizione API di esportazione
description: Ulteriori informazioni sull’API di esportazione import.
products: journeys
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 29%

---


# Utilizzo dell’API Export-Import

Esporta una versione del percorso e tutti i relativi oggetti correlati (percorso, eventi, origini dati, gruppi di campi, azioni personalizzate) con una singola chiamata API. Il payload risultante dall’esportazione può essere utilizzato per importare facilmente il percorso in un altro ambiente (istanza o sandbox).
Questa funzione consente di gestire i percorsi tra più istanze o per più flussi di lavoro di ambienti di test.


## Risorse

L&#39;API Export-Import del Journey Orchestration è descritta all&#39;interno di un file Swagger disponibile [qui](https://adobedocs.github.io/JourneyAPI/docs/).

Per utilizzare questa API con la tua istanza di Journey Orchestration, devi usare la console Adobe I/O. Per iniziare, segui questa procedura [Guida introduttiva alla console Adobe Developer](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) e quindi utilizzare le sezioni in questa pagina.

Per testare e preparare l’integrazione, è disponibile una raccolta Postman [qui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Flusso esportazione-importazione

Per esportare e importare i percorsi negli ambienti, è consigliabile seguire la procedura riportata di seguito.

1. Creare e impostare i parametri di un percorso nell&#39;ambiente di avvio. [Ulteriori informazioni qui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. Verifica se la versione del percorso non contiene errori. [Ulteriori informazioni qui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. Chiamata **/list/percorsi** API per recuperare il percorso UID e l’UID della versione di percorso più recente. Se necessario, puoi chiamare **/percorsi/`{uid}`/più recente** per trovare l’UID dell’ultima versione del percorso.
1. Chiama il **esportare** API con i parametri dell’ambiente di avvio (orgID e sandboxName).
1. Apri il payload di ritorno, quindi controlla i seguenti elementi:
   * Se il percorso esportato contiene **credenziali specifiche**, è necessario sostituire queste credenziali con quelle corrispondenti al nuovo ambiente.
   * Se il percorso esportato contiene **Eventi** che puntano a un **Schema XDM**, se i valori ID sono diversi, devi aggiornare manualmente il riferimento ID schema con l’ID schema del nuovo ambiente nel nodo xdmEntity. Questo aggiornamento deve essere eseguito per ogni evento. [Ulteriori informazioni qui](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * Se il percorso contiene azioni e-mail, sms o push, potrebbe essere necessario aggiornare il nome del modello o il nome di mobileApp se il nome nell’ambiente di destinazione è diverso da quello nell’ambiente di avvio.
1. Chiama il **Importa** API con i parametri dell’ambiente di destinazione (orgID e sandboxName). Puoi richiamare l’API di importazione il numero di volte desiderato. L’UUID e il nome di ciascun oggetto contenuto nel percorso vengono generati ogni volta che si chiama l’API di importazione.
1. Una volta importato il Percorso, potete pubblicarlo nell&#39;applicazione di Journey Orchestration. Ulteriori informazioni [qui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## Autenticazione

### Configurazione dell’accesso alle API

L’accesso alle API di Journey Orchestration è configurato attraverso i passaggi seguenti. Ogni passaggio è descritto in dettaglio nella [Documentazione di Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Per gestire i certificati in Adobe I/O, assicurati di disporre di diritti di <b>Amministratore di sistema</b> dell&#39;organizzazione o di un [account sviluppatore](https://helpx.adobe.com/it/enterprise/using/manage-developers.html) in Admin Console.

1. **Verifica di disporre di un certificato digitale** oppure creane uno, se necessario. Le chiavi pubbliche e private fornite con il certificato sono necessarie nei passaggi seguenti.
1. **Crea una nuova integrazione al servizio [!DNL Journey Orchestration]** in Adobe I/O e configuralo. L’accesso al profilo di prodotto è necessario per Journey Orchestration e Adobe Experience Platform. Quindi saranno generate le credenziali (chiave API, segreto client...).
1. **Crea un token web JSON (JWT)** dalle credenziali generate in precedenza e firmalo con la tua chiave privata. Il JWT codifica tutte le informazioni di identità e sicurezza necessarie ad Adobe per verificare la tua identità e concedere l’accesso all’API. Questo passaggio è descritto in dettaglio in questa [sezione](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Sostituisci il JWT con un token di accesso** tramite una richiesta POST o tramite l’interfaccia Developer Console. Questo token di accesso dovrà essere utilizzato in ogni intestazione delle richieste API.

Per stabilire una sessione API di Adobe I/O servizio-servizio sicura, ogni richiesta a un servizio di Adobe deve includere nell’intestazione dell’autorizzazione le informazioni riportate di seguito.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: si tratta dell’ID organizzazione personale, un ID organizzazione viene fornito da Adobe per ciascuna istanza :

   * &lt;organization> : istanza di produzione

  Per ottenere il valore dell’ID organizzazione, rivolgiti all’amministratore o al contatto tecnico Adobe. È inoltre possibile recuperarlo in Adobe I/O durante la creazione di una nuova integrazione, nell’elenco delle licenze (consulta la [documentazione di Adobe I/O](https://www.adobe.io/authentication.html)).

* **&lt;ACCESS_TOKEN>**: token di accesso personale, che è stato recuperato durante lo scambio del JWT tramite una richiesta POST.

* **&lt;API_KEY>**: la tua chiave API personale. Viene fornita in Adobe I/O dopo la creazione di una nuova integrazione nel servizio [!DNL Journey Orchestration].



## Descrizione API Export-Import

Questa API ti consente di esportare una versione del percorso identificata dal suo UID e tutti gli oggetti correlati (percorso, eventi, origini dati, gruppi di campi, azioni personalizzate) dal suo UID.
Il payload risultante può essere utilizzato per importare la versione del percorso in un altro ambiente (sandbox o istanza).

| Metodo | Percorso | Descrizione |
|---|---|---|
| `[POST]` | /journeyVersions/import | Importa un contenuto di versione del percorso risultante da un&#39;esportazione di versione del percorso |
| `[GET]` | /journeyVersions`{uid}`/export | Esportare una versione del percorso |
| `[GET]` | /percorsi/`{uid}`/più recente | Scarica la versione più recente del percorso per un percorso |
| `[POST]` | /list/percorsi | Elencare i metadati dei percorsi e delle relative versioni di percorso |


### Caratteristiche di esportazione e guardrail

* Il percorso deve essere valido prima dell&#39;esportazione.

* Le credenziali non vengono esportate e un segnaposto (ad esempio, INSERT_SECRET_HERE) viene inserito nel payload di risposta.
Dopo la chiamata di esportazione, è necessario inserire manualmente le nuove credenziali (corrispondenti all’ambiente di destinazione) prima di importare il payload nell’ambiente di destinazione.

* I seguenti oggetti vengono esportati ma non verranno mai importati nell’ambiente di destinazione. Si tratta di risorse di sistema gestite automaticamente dal Journey Orchestration. Non è necessario sostituire &quot;INSERT_SECRET_HERE&quot;.
   * **Fornitori di dati**: &quot;Adobe Campaign Standard Data Provider&quot; (acsDataProvider) e &quot;Experienci Platform&quot; (acppsDataProvider)
   * **Gruppi di campi** (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Caratteristiche di importazione

* Durante l’importazione, gli oggetti del percorso vengono creati con un nuovo UID e un nuovo nome per garantire l’univocità nell’ambiente di destinazione (istanza o sandbox).

* Se il payload di importazione contiene segnaposto segreti, viene generato un errore. È necessario sostituire le informazioni sulle credenziali prima della chiamata POST per importare il percorso.

## Avvertenze ed errori

I potenziali errori sono:

* A **ora di esportazione**, se la versione del percorso non è valida: errore 500

* A **tempo di importazione**, se il payload non è valido dopo le modifiche o se le credenziali non sono ben definite nel payload: errore 400

* Dopo il passaggio di importazione, se l’ID dello schema XDM per gli eventi non è valido nell’ambiente di destinazione, viene visualizzato un errore nell’applicazione di Journey Orchestration. In tal caso non sarà possibile pubblicare il percorso.