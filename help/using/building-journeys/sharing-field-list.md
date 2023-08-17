---
title: Elenco dei campi evento del passaggio
description: Elenco dei campi evento del passaggio
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: b7568080-b88c-415c-9d3f-cc1361664838
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 18%

---

# Elenco dei campi evento del passaggio {#sharing-field-list}

I campi dell’evento del passaggio sono organizzati per categoria.

* Campi delle informazioni di debug
* Campi del percorso
* Campi profilo
* Campi evento del servizio

## debugInfo

| Nome campo | Tipo | Descrizione |
|---|---|------------|
| requestId | Stringa | L’ID richiesta utilizzato dal Journey Orchestration per tenere traccia del flusso di una richiesta. |

## percorso

Questo gruppo di campi viene utilizzato nello schema del percorso (in relazione a journeyStepEvent). Contiene i seguenti campi:

| Nome campo | Tipo | Descrizione |
|---|---|------------|
| ID | Stringa | Identificatore per il Percorso specificato |
| VersionID | Stringa | ID della versione del percorso. Questo ID rappresenta l’identità di un percorso |
| name | Stringa | Nome del percorso |
| descrizione | Stringa | Descrizione del percorso |
| versione | Stringa | versione, rappresentata come `major`.`minor` |

## profilo

Questo gruppo di campi è specifico di journeyStepEvent: questo evento è in relazione con il percorso e non dispone di identityMap che descrive l’eventuale identità del profilo.

Per journeyStepEvent, è inoltre necessario aggiungere campi relativi all’identità:

| Nome campo | Tipo | Descrizione |
|---|---|------------|
| ID | Stringa | L’identificatore del profilo identifica il profilo inviato/utilizzato in un percorso. Esempio: foo@adobe.com. |
| namespace | Stringa | Questo campo descrive lo spazio dei nomi a cui fa riferimento il profilo utilizzato nel Percorso. Ad esempio: E-mail, ECID |

## serviceEvents

Questo mixin contiene tutti i campi corrispondenti a un processo di esportazione profilo.

| Nome campo | Tipo | Descrizione |
|---|---|------------|
| ID | Stringa | Identificatore del processo di esportazione del segmento attivato |
| stato | Stringa | Lo stato del processo di esportazione del segmento: in coda, avviato, completato |
| exportCountTotal | Intero | Il valore massimo possibile del processo di esportazione del segmento |
| exportCountRealized | Intero | Numero effettivo di segmenti esportati tramite il processo |
| exportCountFailed | Intero | Numero di segmenti non riusciti durante l’esportazione nel processo |
| exportSegmentID | Stringa | Identificatore del segmento da esportare |
| eventType | Stringa | Tipo di evento che indica se si tratta di un evento di errore di evento informazioni: Info, Error |
| eventCode | Stringa | Codice di errore che indica il motivo del tipo di evento corrispondente |

## stepEvents

Questa categoria contiene i campi dell’evento del passaggio originale. Consulta questa [sezione](../building-journeys/sharing-legacy-fields.md).
