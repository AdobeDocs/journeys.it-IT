---
title: eventi dei passi di viaggio, campi comuni
description: eventi dei passi di viaggio, campi comuni
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---


# journeysteps events common fields {#sharing-common-fields}

Questo mixin sarà condiviso da pathStepEvent e pathStepProfileEvent.

Si tratta dei campi XDM più comuni che [!DNL Journey Orchestration] vengono inviati ad Adobe Experience Platform. Verranno inviati campi comuni per ogni fase elaborata durante un viaggio. Campi più specifici vengono utilizzati per azioni personalizzate e per arricchimenti.

Alcuni di questi campi sono disponibili solo in pattern di elaborazione specifici (esecuzione delle azioni, recupero dei dati, ecc.) per limitare la dimensione degli eventi.

## ingresso

Indica se l’utente è entrato nel percorso. Se non è presente, si presuppone che il valore sia falso.

Tipo: boolean

Valori: true/false

## rientro

Indica se l’utente è rientrato nel percorso con la stessa istanza. Se non è presente, si presuppone che il valore sia falso.

Tipo: boolean

Valori: true/false

## instanceEnded

Indica se l&#39;istanza è terminata (o meno).

Tipo: boolean

## eventID

ID evento nell&#39;elaborazione, per l&#39;elaborazione dei passaggi. Se l&#39;evento è esterno, il valore è il relativo eventId. Se l&#39;evento è interno, il valore è l&#39;eventId interno (ad esempio, ScheduledNotificationReceived, executeAction, ecc.).

Tipo: string

## nodeID

ID nodo client (dal quadro).

Tipo: string

## stepID

ID univoco del passaggio in corso di elaborazione.

Tipo: string

## stepName

Nome del passaggio in corso di elaborazione.

Tipo: string

## stepType

Tipo del passaggio.

Tipo: string

Valori possibili:

* Condizione
* Azione
* Scheduler
* Timer

## stepStatus

Stato del passaggio, che rappresenta lo stato del passo, al termine dell&#39;elaborazione (e all&#39;attivazione dell&#39;evento step).

Tipo: string

Lo stato può essere:

* ended: il passaggio non ha alcuna transizione ed è terminata l&#39;elaborazione.
* error: l&#39;elaborazione dei passaggi ha generato un errore.
* transizioni: il passaggio è in attesa della transizione di un evento a un altro passaggio.
* con cappuccio: il passaggio non è riuscito in caso di errore di limitazione, generato durante un&#39;azione o un arricchimento.
* timeout: il passaggio non è riuscito in caso di errore di timeout, generato durante un&#39;azione o un arricchimento.
* instanceTimedout: l&#39;elaborazione del passaggio è stata interrotta perché l&#39;istanza ha raggiunto il timeout.

## viaggioID

ID del viaggio.

Tipo: string

## viaggioVersionID

ID della versione del viaggio. Questo ID rappresenta il riferimento dell&#39;identità al percorso, nel caso del viaggioStepEvent.

Tipo: string

## viaggioVersionName

Nome della versione del viaggio.

Tipo: string

## viaggioVersion

Versione del percorso.

Tipo: string

## instanceID

ID interno dell’istanza di viaggio.

Tipo: string

## externalKey

Chiave esterna estratta dall’evento per elaborarlo.

Tipo: string

## parentStepID

ID passo dell&#39;elemento padre del passaggio elaborato corrente nell&#39;istanza.

Tipo: string

## parentStepName

Nome del passo dell&#39;elemento padre del passaggio corrente.

Tipo: string

## parentTransitionID

Id della transizione che ha portato l&#39;istanza al passaggio elaborato.

Tipo: string

## parentTransitionName

Nome della transizione che ha portato l&#39;istanza al passaggio elaborato.

Tipo: string

## inTest

Indicato se il viaggio è in modalità di prova o meno.

Tipo: boolean

## processingTime

Quantità totale di tempo, in millisecondi, dall&#39;entrata del passaggio dell&#39;istanza alla fine dell&#39;elaborazione.

Tipo: long

## instanceType

Indica il tipo di istanza, se è batch o unitario.

Tipo: string

Valori: batch/unitario

## variationIndex

Indice della ricorrenza se il percorso è batch e ricorrente (la prima esecuzione ha indice di ricorrenza = 1).

Tipo: long

## isBatchToUnitaria

Indica se l&#39;istanza unitaria è stata attivata da un&#39;istanza batch.

Tipo: boolean

## batchExternalKey

Chiave esterna per l&#39;evento batch.

Tipo: string

## batchInstanceID

questo è l&#39;ID dell&#39;istanza batch.

Tipo: string

## batchUnitariaBranchID

se l’istanza è stata attivata da un’istanza batch, ID ramo unitario.

Tipo: string
