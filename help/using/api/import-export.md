---
product: adobe campaign
title: Descrizione dell’API di esportazione di importazione
description: Ulteriori informazioni sull’API di esportazione dell’importazione.
products: journeys
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 1%

---


# Utilizzo dell’API Export-Import

Esporta una versione del percorso e tutti gli oggetti correlati (percorso, eventi, origini dati, gruppi di campi, azioni personalizzate) con una singola chiamata API. Il payload risultante dall’esportazione può essere utilizzato per importare facilmente il percorso in un altro ambiente (istanza o sandbox).
Questa funzione consente di gestire i percorsi in più istanze o per più flussi di lavoro di ambienti di test.


## Risorse

L’API Export-Import del Journey Orchestration è descritta all’interno di un file Swagger disponibile [qui](https://adobedocs.github.io/JourneyAPI/docs/).

Per utilizzare questa API con l’istanza di Journey Orchestration, è necessario utilizzare la console AdobeI/O. Per iniziare, segui questo [Guida introduttiva alla console Adobe Developer](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) e quindi utilizzare le sezioni di questa pagina.

Per testare e preparare l’integrazione è disponibile una raccolta Postman [qui](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Flusso di esportazione-importazione

Per esportare e importare i percorsi tra ambienti, si consiglia di seguire questi passaggi:

1. Crea e imposta il parametro di un percorso nell’ambiente di avvio. [Maggiori informazioni qui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. Controlla se la versione del percorso non contiene errori. [Maggiori informazioni qui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. Chiamata **/elenco/percorsi** API per recuperare il percorso UID e l’UID della versione più recente del percorso. Se necessario, puoi chiamare **/percorsi/`{uid}`/più recente** per trovare l’UID della versione di percorso più recente.
1. Chiama il **esportare** API con i parametri dell’ambiente di avvio (orgID e sandboxName).
1. Apri il payload restituito, quindi controlla i seguenti elementi:
   * Se il percorso esportato contiene **credenziali specifiche**, devi sostituire queste credenziali con quelle corrispondenti al nuovo ambiente.
   * Se il percorso esportato contiene **events** che indicano **Schema XDM**, se i valori ID sono diversi, devi aggiornare manualmente il riferimento dell’ID schema con l’ID schema del nuovo ambiente nel nodo xdmEntity . Questo aggiornamento deve essere fatto per ogni evento. [Maggiori informazioni qui](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * Se il percorso contiene azioni e-mail, sms o push, potrebbe essere necessario aggiornare il nome del modello o il nome dell’app mobile se il nome nell’ambiente di destinazione è diverso da quello nell’ambiente di avvio.
1. Chiama il **Importa** API con i parametri dell’ambiente di destinazione (orgID e sandboxName). Puoi richiamare l’API di importazione il numero di volte che desideri. L’UUID e il nome di ciascun oggetto contenuto nel percorso vengono generati ogni volta che si chiama l’API di importazione.
1. Una volta importato il Percorso, puoi pubblicarlo nell’applicazione di Journey Orchestration. Ulteriori informazioni [qui](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## Autenticazione

### Impostazione dell’accesso alle API

L’accesso API di Journey Orchestration è configurato attraverso i passaggi seguenti. Ciascuno di questi passaggi è descritto nella sezione [Documentazione di Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Per gestire i certificati in Adobe I/O, assicurati di disporre di <b>Amministratore di sistema</b> diritti dell&#39;organizzazione o [account sviluppatore](https://helpx.adobe.com/it/enterprise/using/manage-developers.html) in Admin Console.

1. **Verifica di disporre di un certificato digitale** oppure creane uno, se necessario. Le chiavi pubbliche e private fornite con il certificato sono necessarie nei passaggi seguenti.
1. **Creare una nuova integrazione in [!DNL Journey Orchestration] Servizio** in Adobe I/O e configuralo. L’accesso al profilo di prodotto è necessario per Journey Orchestration e Adobe Experience Platform. Le credenziali verranno quindi generate (chiave API, segreto client...).
1. **Creare un token web JSON (JWT)** dalle credenziali generate in precedenza e firmalo con la tua chiave privata. JWT codifica tutte le informazioni di identità e sicurezza necessarie per Adobe per verificare la tua identità e concedere l’accesso all’API. Questo passaggio è descritto in [sezione](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Sostituire il JWT con un token di accesso** tramite una richiesta POST o tramite l’interfaccia Console per sviluppatori. Questo token di accesso dovrà essere utilizzato in ogni intestazione delle richieste API.

Per stabilire una sessione API di Adobe I/O servizio-servizio sicura, ogni richiesta a un servizio Adobe deve includere nell’intestazione Autorizzazione le informazioni riportate di seguito.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Si tratta dell’ID organizzazione personale, un ID organizzazione viene fornito per Adobe per ciascuna istanza :

   * &lt;organization> : l&#39;istanza di produzione
   Per ottenere il valore dell’ID ORGANIZZAZIONE, rivolgiti all’amministratore o al contatto tecnico Adobe. È inoltre possibile recuperarlo in Adobe I/O durante la creazione di una nuova integrazione, nell&#39;elenco delle licenze (consulta [Documentazione di Adobe I/O](https://www.adobe.io/authentication.html)).

* **&lt;access_token>**: Token di accesso personale, recuperato durante lo scambio di JWT tramite una richiesta POST.

* **&lt;api_key>**: la tua chiave API personale. Viene fornito in Adobe I/O dopo la creazione di una nuova integrazione in [!DNL Journey Orchestration] Servizio.



## Descrizione dell’API Export-Import

Questa API ti consente di esportare per l’ID di un percorso una versione identificata dal relativo UID e tutti gli oggetti correlati (percorso, eventi, origini dati, gruppi di campi, azioni personalizzate).
Il payload risultante può essere utilizzato per importare la versione di percorso in un altro ambiente (sandbox o istanza).

| Metodo | Path | Descrizione |
|---|---|---|
| `[POST]` | /journeyVersions/import | Importare un contenuto di versione di un percorso risultante da un’esportazione di versioni di un percorso |
| `[GET]` | /journeyVersions/`{uid}`/export | Esportare una versione di percorso |
| `[GET]` | /percorsi/`{uid}`/più recente | Scarica la versione di percorso più recente per un percorso |
| `[POST]` | /elenco/percorsi | Elencare i metadati dei percorsi e delle relative versioni percorso |


### Caratteristiche di esportazione e protezioni

* Il percorso deve essere valido prima dell&#39;esportazione.

* Le credenziali non vengono esportate e un segnaposto (ad esempio INSERT_SECRET_HERE) viene inserito nel payload della risposta.
Dopo la chiamata di esportazione, è necessario inserire manualmente le nuove credenziali (corrispondenti all’ambiente di destinazione) prima di importare il payload nell’ambiente di destinazione.

* I seguenti oggetti vengono esportati ma non verranno mai importati nell’ambiente di destinazione. Si tratta di risorse di sistema gestite automaticamente dal Journey Orchestration. Non è necessario sostituire &quot;INSERT_SECRET_HERE&quot;.
   * **DataProvider**: &quot;Adobe Campaign Standard Data Provider&quot; (acsDataProvider) e &quot;Experience Platform&quot; (acppsDataProvider)
   * **Gruppi di campi** (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Caratteristiche di importazione

* Durante l’importazione, gli oggetti percorso vengono creati con un nuovo UID e un nuovo nome per garantire l’univocità nell’ambiente di destinazione (istanza o sandbox).

* Se il payload di importazione contiene segnaposto segreti, viene generato un errore. Per importare il percorso, è necessario sostituire le informazioni sulle credenziali prima della chiamata POST .

## Avvisi ed errori

Gli errori potenziali sono:

* A **tempo di esportazione**, se la versione del percorso non è valida : errore 500

* A **tempo di importazione**, se il payload non è valido dopo le modifiche o se le credenziali non sono ben definite nel payload : errore 400

* Dopo il passaggio di importazione, se l’ID dello schema XDM per gli eventi non è valido nell’ambiente di destinazione, nell’applicazione di Journey Orchestration viene visualizzato un errore. In tal caso non sarà possibile pubblicare il percorso.