---
product: adobe campaign
title: Proprietà del percorso
description: Informazioni sulle proprietà del percorso
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 6%

---

# Attributi proprietà percorso {#journey-properties}

Nell’editor di espressioni avanzate, troverai **Proprietà percorso** sotto le categorie evento e origine dati. Questa categoria contiene campi tecnici relativi al percorso per un determinato profilo. Si tratta delle informazioni che il sistema recupera dai percorsi in tempo reale, ad esempio l’ID percorso o specifici errori rilevati.

>[!NOTE]
>
>Gli attributi delle proprietà del percorso sono disponibili anche nell’editor di espressioni semplici. Consulta questa [sezione](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

Troverai informazioni, ad esempio, su:

* versione percorso: uid percorso, uid versione percorso, uid istanza, ecc.
* errori: recupero dati, esecuzione azione, ecc.
* passaggio corrente, ultimo passaggio corrente, ecc.
* profili scartati

Puoi utilizzare questi campi per creare espressioni. Durante l’esecuzione del percorso, i valori vengono recuperati direttamente dal percorso.

Di seguito sono riportati alcuni esempi di casi di utilizzo:

* **Registra profili eliminati**: puoi inviare a un sistema di terze parti tutti i profili esclusi da un messaggio da una regola di limitazione di utilizzo a scopo di registrazione. A questo scopo, imposta un percorso in caso di timeout ed errore e aggiungi una condizione per filtrare in base a un tipo di errore specifico, ad esempio: &quot;elimina le persone applicando una regola di limite&quot;. Puoi quindi inviare i profili eliminati a un sistema di terze parti tramite un’azione personalizzata.

* **Invia avvisi in caso di errori**: puoi inviare una notifica a un sistema di terze parti ogni volta che si verifica un errore in un messaggio. A questo scopo, puoi impostare un percorso in caso di errore, aggiungere una condizione e un’azione personalizzata. Puoi inviare una notifica su un canale di Slack, ad esempio, con la descrizione dell’errore riscontrato.

* **Perfezionare gli errori nella generazione rapporti** : invece di disporre di un solo percorso per i messaggi con errore, puoi definire una condizione per tipo di errore. In questo modo sarà possibile perfezionare la generazione rapporti e visualizzare tutti i dati relativi ai tipi di errore.

## Elenco dei campi {#journey-properties-fields}

| Categoria | Nome campo | Etichetta | Descrizione |
|---|---|---|------------|
| Versione percorso | journeyUID | Identificatore percorso |  |
|  | journeyVersionUID | Identificatore versione percorso |  |
|  | journeyVersionName | Nome versione percorso |  |
|  | journeyVersionDescription | Descrizione versione percorso |  |
|  | journeyVersion | Versione percorso |  |
| Istanza percorso | instanceUID | Identificatore istanza percorso | ID dell’istanza |
|  | externalKey | Chiave esterna | Identificatore individuale che attiva il percorso |
|  | organizationId | Identificatore organizzazione | Organizzazione del brand |
|  | sandboxName | Nome della sandbox | Nome della sandbox |
| Identità | profileId | Identificatore dell’identità del profilo | Identificatore del profilo nel percorso |
|  | namespace | Spazio dei nomi identità profilo | Spazio dei nomi del profilo nel percorso (ad esempio: ECID) |
| Nodo corrente | currentNodeId | Identificatore nodo corrente | Identificatore dell’attività corrente (nodo) |
|  | currentNodeName | Nome nodo corrente | Nome dell’attività corrente (nodo) |
| Nodo precedente | previousNodeId | Identificatore nodo precedente | Identificatore dell’attività precedente (nodo) |
|  | previousNodeName | Nome nodo precedente | Nome dell’attività precedente (nodo) |
| Errori | lastNodeUIDInError | Identificatore ultimo nodo in errore | Identificatore dell’attività (nodo) più recente con errore |
|  | lastNodeNameInError | Nome ultimo nodo in errore | Nome dell’attività (nodo) più recente con errore |
|  | lastNodeTypeInError | Ultimo tipo di nodo in errore | Tipo di errore dell’attività (nodo) più recente nell’errore. Tipi possibili:<ul><li>Eventi: Eventi, Reazioni, SQ (ad esempio: Qualificazione del segmento)</li><li>Controllo del flusso: Fine, Condizione, Attesa</li><li>Azioni: azioni ACS, Salta, Azione personalizzata</li></ul> |
|  | lastErrorCode | Codice ultimo errore | Codice di errore dell’attività (nodo) più recente che presenta un errore. Possibili errori: <ul><li>Codici di errore HTTP</li><li>con limite</li><li>timeout</li><li>error (esempio: default in caso di errore imprevisto. Non deve/raramente si verifica)</li></ul> |
|  | lastExecutedActionErrorCode | Codice errore ultima azione eseguita | Codice di errore dell’ultima azione in errore |
|  | lastDataFetchErrorCode | Codice errore ultimo recupero dati | Codice di errore dell’ultimo recupero dati da origini dati |
| Ora | lastActionExecutionElapsedTime | Tempo trascorso dall’esecuzione dell’ultima azione | Tempo impiegato per eseguire l’azione più recente |
|  | lastDataFetchElapsedTime | Tempo trascorso dall’ultimo recupero dati | Tempo impiegato per eseguire l’ultimo recupero dati dalle origini dati |
