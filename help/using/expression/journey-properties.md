---
product: adobe campaign
solution: Journey Orchestration
title: Proprietà del percorso
description: Scopri le proprietà del viaggio
translation-type: tm+mt
source-git-commit: 341138c31676870878099b4f4eecec200a614c69
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 1%

---


# Proprietà del percorso {#journey-properties}

Nell&#39;editor di espressioni avanzate, sotto le categorie dell&#39;evento e dell&#39;origine dati si trova la categoria **Proprietà percorso**. Questa categoria contiene i campi tecnici relativi al percorso di un determinato profilo. Si tratta delle informazioni recuperate dal sistema dai viaggi in diretta, come l&#39;ID viaggio o gli errori specifici riscontrati.

![](../assets/journey-properties.png)

Troverete informazioni, ad esempio:

* versione viaggio: viaggio uid, versione percorso uid, esempio uid, ecc.
* errori: acquisizione dei dati, esecuzione di azioni, ecc.
* passaggio corrente, ultimo passaggio corrente, ecc.
* profili eliminati

È possibile utilizzare questi campi per creare espressioni. Durante l&#39;esecuzione del viaggio, i valori saranno recuperati direttamente dal viaggio.

Di seguito sono riportati alcuni esempi di casi di utilizzo:

* **Profili** eliminati dal registro: puoi inviare tutti i profili esclusi da un messaggio tramite una regola di capping a un sistema di terze parti a scopo di registrazione. A questo scopo, configurate un percorso in caso di timeout ed errore e aggiungete una condizione per filtrare in base a un tipo di errore specifico, ad esempio: &quot;elimina le persone con la regola di capping&quot;. Potete quindi inviare i profili eliminati a un sistema di terze parti tramite un&#39;azione personalizzata.

* **Invia avvisi in caso di errori**: puoi inviare una notifica a un sistema di terze parti ogni volta che si verifica un errore in un messaggio. A questo scopo, potete impostare un percorso in caso di errore, aggiungere una condizione e un&#39;azione personalizzata. Potete inviare una notifica su un canale di Slack , ad esempio, con la descrizione dell&#39;errore rilevato.

* **Ottimizzazione degli errori nel reporting** : invece di avere un solo percorso per i messaggi di errore, puoi definire una condizione per tipo di errore. In questo modo sarà possibile perfezionare il reporting e visualizzare tutti i dati dei tipi di errore.

## Elenco di campi {#journey-properties-fields}

| Categoria | Nome campo | Etichetta | Descrizione |
|---|---|---|------------|
| Versione percorso | viaggioUID | Identificatore percorso |  |
|  | viaggioVersionUID | Identificatore versione viaggio |  |
|  | viaggioVersionName | Nome versione viaggio |  |
|  | pathVersionDescription | Descrizione versione viaggio |  |
|  | viaggioVersion | Versione percorso |  |
| Istanza di viaggio | instanceUID | Identificatore Istanza Del Percorso | ID dell’istanza |
|  | externalKey | Chiave esterna | Singolo identificatore che attiva il percorso |
| Identità | profileId | Identificatore identità profilo | Identificatore del profilo nel percorso |
|  | namespace | Spazio dei nomi identità profilo | Spazio dei nomi del profilo nel percorso (esempio: ECID |
| Nodo corrente | currentNodeId | Identificatore nodo corrente | Identificatore dell&#39;attività corrente (nodo) |
|  | currentNodeName | Nome nodo corrente | Nome dell&#39;attività corrente (nodo) |
| Nodo precedente | previousNodeId | Identificatore nodo precedente | Identificatore dell&#39;attività precedente (nodo) |
|  | previousNodeName | Nome nodo precedente | Nome dell&#39;attività precedente (nodo) |
| Errori | lastNodeUIDInError | Identificatore ultimo nodo in errore | Identificatore dell&#39;attività più recente (nodo) in errore |
|  | lastNodeNameInError | Nome ultimo nodo in errore | Nome dell&#39;attività più recente (nodo) in errore |
|  | lastNodeTypeInError | Ultimo tipo di nodo in errore | Tipo di errore dell&#39;ultima attività (nodo) in errore. Tipi possibili:<ul><li>Eventi: Eventi, Reazioni, SQ (esempio: Qualificazione segmento)</li><li>Controllo del flusso: Fine, Condizione, Aspetta</li><li>Azioni: Azioni ACS, Jump, Azione personalizzata</li></ul> |
|  | lastErrorCode | Ultimo codice di errore | Codice di errore dell&#39;ultima attività (nodo) in errore. Possibili errori: <ul><li>Codici di errore HTTP</li><li>con cappuccio</li><li>timedOut</li><li>error (esempio: predefinito in caso di errore imprevisto. Non dovrebbe/estremamente raro)</li></ul> |
|  | lastExecuteActionErrorCode | Codice errore ultima azione eseguita | Codice di errore dell&#39;ultima azione in errore |
|  | lastDataFetchErrorCode | Codice errore ultimo recupero dati | Codice di errore del recupero dati più recente da origini dati |
| Time | lastActionExecutionElapsedTime | Tempo trascorso ultima esecuzione azione | Tempo impiegato per eseguire l&#39;azione più recente |
|  | lastDataFetchElapsedTime | Tempo trascorso ultimo recupero dati | Tempo impiegato per eseguire il recupero dati più recente da origini dati |
