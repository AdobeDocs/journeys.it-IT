---
product: adobe campaign
title: Proprietà del percorso
description: Scopri sulle proprietà del percorso
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 3%

---

# Attributi delle proprietà del percorso {#journey-properties}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy sostituiti da Journey Optimizer. Contatta il tuo team account se hai domande sulle accesso a Journey Orchestration o Journey Optimizer._


Nella editor espressioni avanzate è disponibile la **categoria Journey Proprietà** , sotto le categorie di eventi e origini dati. Questa categoria contiene campi tecnici relativi al percorso per un determinato profilo. Si tratta delle informazioni recuperate dal sistema dai viaggi in tempo reale, come l&#39;ID del viaggio o gli errori specifici riscontrati.

>[!NOTE]
>
>Gli attributi delle proprietà percorso sono disponibili anche nell&#39;espressione semplice editor. Consulta questa [sezione](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

Troverai informazioni, ad esempio, su:

* versione percorso: uid percorso, uid versione percorso, uid istanza, ecc.
* errori: recupero dati, esecuzione azione, ecc.
* passaggio corrente, ultimo passaggio corrente, ecc.
* profili scartati

Puoi utilizzare questi campi per creare espressioni. Durante l’esecuzione del percorso, i valori vengono recuperati direttamente dal percorso.

Di seguito sono riportati alcuni esempi di casi di utilizzo:

* **Registra profili scartati**: puoi inviare tutti i profili esclusi da un messaggio da una regola di limitazione a un sistema di terze parti a scopo di registrazione. A questo scopo, imposta un percorso in caso di timeout ed errore e aggiungi una condizione per filtrare in base a un tipo di errore specifico, ad esempio: &quot;elimina le persone applicando una regola di limite&quot;. Puoi quindi inviare i profili eliminati a un sistema di terze parti tramite un’azione personalizzata.

* **Invia avvisi in caso di errori**: è possibile inviare una notifica a un sistema di terze parti ogni volta che si verifica un errore in un messaggio. A questo scopo, puoi impostare un percorso in caso di errore, aggiungere una condizione e un’azione personalizzata. Puoi inviare una notifica su un canale Slack, ad esempio, con la descrizione dell’errore riscontrato.

* **Perfezionare gli errori nella generazione dei rapporti**: invece di disporre di un solo percorso per i messaggi in errore, è possibile definire una condizione per tipo di errore. In questo modo sarà possibile perfezionare la generazione rapporti e visualizzare tutti i dati relativi ai tipi di errore.

## Elenco dei campi {#journey-properties-fields}

| Categoria | Nome campo | Etichetta | Descrizione |
|---|---|---|------------|
| Versione percorso | journeyUID | Identificatore percorso | |
| | journeyVersionUID | Identificatore Versione percorso | |
| | NomeVersione viaggio | Nome Versione percorso | |
| | journeyVersionDescription | Viaggio Versione Descrizione | |
| | journeyVersion | Viaggio Versione | |
| Istanza percorso | instanceUID | Identificatore istanza percorso | ID del istanza |
| | Chiave esterna | Chiave esterna | Identificatore individuale che attiva il percorso |
| | organizationId | Identificatore dell’organizzazione | Organizzazione del marchio |
| | Nome sandbox | Nome sandbox | Nome della sandbox |
| Identità | ID profilo | Identificatore identità profilo | Identificatore del profilo durante il percorso |
| | Namespace | Namespace Identità profilo | Namespace del profilo nel percorso (esempio: ECID) |
| Nodo corrente | currentNodeId | Identificatore nodo corrente | Identificatore dell&#39;attività corrente (nodo) |
| | Nome nodo corrente | Nome nodo corrente | Nome dell&#39;attività corrente (nodo) |
| Precedente nodo | previousNodeId | Identificatore nodo Precedente | Identificatore dell&#39;attività precedente (nodo) |
| | previousNodeName | Nome nodo precedente | Nome dell’attività precedente (nodo) |
| Errori | lastNodeUIDInError | Identificatore ultimo nodo in errore | Identificatore dell’attività (nodo) più recente con errore |
| | lastNodeNameInError | Nome ultimo nodo in errore | Nome dell’attività (nodo) più recente con errore |
| | lastNodeTypeInError | Ultimo tipo di nodo in errore | Tipo di errore dell’attività (nodo) più recente nell’errore. Tipi possibili:<ul><li>Eventi: Eventi, Reazioni, SQ (esempio: qualificazione segmento)</li><li>Controllo Flusso: Fine, Condizione, Attesa</li><li>Azioni: Azioni ACS, Salta, Azione personalizzata</li></ul> |
| | lastErrorCode | Codice ultimo errore | Codice di errore dell’attività (nodo) più recente che presenta un errore. Possibili errori: <ul><li>Codici di errore HTTP</li><li>con limite</li><li>timedOut</li><li>errore (esempio: impostazione predefinita in caso di errore imprevisto. Non dovrebbe/accadrà molto raramente)</li></ul> |
| | lastExecutedActionErrorCode | Ultima azione eseguita Errore Code | Errore codice dell&#39;ultima azione per errore |
| | lastDataFetchErrorCode | Codice errore ultimo recupero dati | Codice di errore dell’ultimo recupero dati da origini dati |
| Ora | lastActionExecutionElapsedTime | Tempo trascorso dall’esecuzione dell’ultima azione | Tempo impiegato per eseguire l’azione più recente |
| | lastDataFetchElapsedTime | Tempo trascorso dall’ultimo recupero dati | Tempo impiegato per eseguire l’ultimo recupero dati dalle origini dati |
