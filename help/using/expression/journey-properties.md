---
product: adobe campaign
solution: Journey Orchestration
title: Proprietà del viaggio
description: Scopri le proprietà del viaggio
translation-type: tm+mt
source-git-commit: 1fd02fcc2a535046cfbcdb5d1c52850ee93370af
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---


# Proprietà del viaggio {#journey-properties}

Nell&#39;editor di espressioni avanzate, sotto le categorie dell&#39;evento e dell&#39;origine dati si trova la categoria Proprietà **** viaggio. Questa categoria contiene i campi tecnici relativi al percorso di un determinato profilo. Si tratta delle informazioni recuperate dal sistema dai viaggi in diretta, come l&#39;ID viaggio o gli errori specifici riscontrati.

![](../assets/journey-properties.png)

Troverete informazioni, ad esempio:

* versione viaggio: viaggio uid, versione percorso uid, esempio uid, ecc.
* errori: acquisizione dei dati, esecuzione di azioni, ecc.
* passaggio corrente, ultimo passaggio corrente, ecc.
* profili eliminati

È possibile utilizzare questi campi per creare espressioni. Durante l&#39;esecuzione del viaggio, i valori saranno recuperati direttamente dal viaggio.

Di seguito sono riportati alcuni esempi di casi di utilizzo:

* **Profili** eliminati dal registro: puoi inviare tutti i profili esclusi da un messaggio tramite una regola di capping a un sistema di terze parti a scopo di registrazione. A questo scopo, configurate un percorso in caso di timeout ed errore e aggiungete una condizione per filtrare in base a un tipo di errore specifico, ad esempio: &quot;elimina le persone con la regola di capping&quot;. Potete quindi inviare i profili eliminati a un sistema di terze parti tramite un&#39;azione personalizzata.

* **Invio di avvisi push in caso di errori**: puoi inviare una notifica a un sistema di terze parti ogni volta che si verifica un errore in un messaggio. A questo scopo, potete impostare un percorso in caso di errore, aggiungere una condizione e un&#39;azione personalizzata. Potete inviare una notifica su un canale di Slack , ad esempio, con la descrizione dell&#39;errore rilevato.

* **Ottimizzazione degli errori nei report** : invece di avere un solo percorso per i messaggi di errore, puoi definire una condizione per tipo di errore. In questo modo sarà possibile perfezionare il reporting e visualizzare tutti i dati dei tipi di errore.

## Elenco di campi {#journey-properties-fields}

|Categoria|Nome campo|Etichetta|Descrizione|
|-|-|-|—|
|Versione percorso|UID percorso|Identificatore percorso| |
| |viaggioVersioneUID|Identificatore versione viaggio| |
| |viaggioVersionName|Nome versione viaggio| |
| |pathVersionDescription|Descrizione versione viaggio| |
| |tripVersion|Journey Version| |
|Istanza di viaggio|instanceUID|Identificatore istanza di viaggio|ID dell&#39;istanza|
| |externalKey|Chiave esterna|Identificatore individuale che attiva il percorso|
|Identità|profileId|Identificatore identità profilo|Identificatore del profilo nel percorso|
| |namespace|Spazio dei nomi identità profilo|Spazio dei nomi del profilo nel percorso (esempio: ECID)|
|Nodo corrente|currentNodeId|Identificatore nodo corrente|Identificatore dell&#39;attività corrente (nodo)|
| |currentNodeName|Nome nodo corrente|Nome dell&#39;attività corrente (nodo)|
|Nodo precedente|previousNodeId|Identificatore nodo precedente|Identificatore dell&#39;attività precedente (nodo)|
| |previousNodeName|Nome nodo precedente|Nome dell&#39;attività precedente (nodo)|
|Errori|lastNodeUIDInError|Last Node Identifier in Error|Identifier of the most activity (node) in error|
| |lastNodeNameInError|Last Node Name in Error|Nome dell&#39;ultima attività (nodo) in error|
| |lastNodeTypeInError|Last Node Type in Error|Error type dell&#39;ultima attività (nodo) in error. Tipi possibili:<ul><li>Eventi: Eventi, Reazioni, SQ (esempio: Qualificazione segmento)</li><li>Controllo del flusso: Fine, Condizione, Aspetta</li><li>Azioni: Azioni ACS, Jump, Azione personalizzata</li></ul>|
| |lastErrorCode|Last Error Code|Error code|Error code of the last activity (node) in error. Possibili errori: <ul><li>Codici di errore HTTP</li><li>con cappuccio</li><li>timedOut</li><li>error (esempio: predefinito in caso di errore imprevisto. Non dovrebbe/estremamente raro)</li></ul>|
| |lastExecutingActionErrorCode|Last Execution Action Error Code|Error code dell&#39;ultima azione eseguita in errore |
| |lastDataFetchErrorCode|Last Data Fetch Error Code|Codice errore ultimo recupero dati|Codice errore del recupero dati più recente da origini dati|
|Tempo|lastActionExecutionElapsedTime|Tempo trascorso dell&#39;ultima esecuzione dell&#39;azione|Tempo trascorso per eseguire l&#39;ultima azione|
| |lastDataFetchElapsedTime|Ultimo recupero dati trascorso|Tempo trascorso per eseguire il recupero dati più recente da origini dati|
