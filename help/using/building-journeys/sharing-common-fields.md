---
product: adobe campaign
title: Campi comuni degli eventi di journeyStep
description: Campi comuni degli eventi di journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# Campi comuni degli eventi di journeyStep {#sharing-common-fields}

Questo mixin sarà condiviso da journeyStepEvent e journeyStepProfileEvent.

Si tratta dei campi XDM comuni che [!DNL Journey Orchestration] invia a Adobe Experience Platform. Verranno inviati campi comuni per ogni passaggio elaborato in un percorso. Campi più specifici vengono utilizzati per azioni personalizzate e arricchimenti.

Alcuni di questi campi sono disponibili solo in pattern di elaborazione specifici (esecuzione azione, recupero dati, ecc.) per limitare le dimensioni degli eventi.

## ingresso

Indica se l’utente è entrato nel percorso. Se non è presente, si presuppone che il valore sia falso.

Tipo: booleano

Valori: true/false

## rientro

Indica se l’utente è rientrato nel percorso con la stessa istanza. Se non è presente, si presuppone che il valore sia falso.

Tipo: booleano

Valori: true/false

## instanceEnded

Indica se l&#39;istanza è terminata (con successo o meno).

Tipo: booleano

## eventID

ID evento in elaborazione, per l’elaborazione dei passaggi. Se l’evento è esterno, il valore è il relativo eventId. Se l’evento è interno, il valore è l’ID evento interno (ad esempio, scheduledNotificationReceived, executeAction, ecc.).

Tipo: string

## nodeID

ID nodo client (dall’area di lavoro).

Tipo: string

## stepID

ID univoco del passaggio in fase di elaborazione.

Tipo: string

## stepName

Nome del passaggio attualmente in fase di elaborazione.

Tipo: string

## stepType

Tipo del passaggio.

Tipo: string

Valori possibili:

* Condizione
* Azione
* Attività Scheduler
* Timer

## stepStatus

Stato del passaggio, che rappresenta lo stato del passaggio, al termine dell’elaborazione (e all’avvio dell’evento step).

Tipo: string

Lo stato può essere:

* end: il passaggio non ha alcuna transizione e l’elaborazione è terminata correttamente.
* errore: errore generato dall&#39;elaborazione dei passaggi.
* transizioni: il passaggio è in attesa della transizione di un evento a un altro passaggio.
* con limiti massimi: il passaggio non è riuscito per un errore di limitazione, generato durante un&#39;azione o un arricchimento.
* timeout: il passaggio non è riuscito per un errore di timeout, generato durante un&#39;azione o un arricchimento.
* instanceTimedout: il passaggio ha interrotto l’elaborazione perché l’istanza ha raggiunto il timeout.

## journeyID

ID del percorso.

Tipo: string

## journeyVersionID

ID della versione del percorso. Questo id rappresenta il riferimento di identità al percorso, nel caso di journeyStepEvent.

Tipo: string

## journeyVersionName

Nome della versione del percorso.

Tipo: string

## journeyVersion

Versione del percorso.

Tipo: string

## instanceID

ID interno dell&#39;istanza del percorso.

Tipo: string

## externalKey

Chiave esterna estratta dall’evento per elaborarla.

Tipo: string

## parentStepID

ID del passo padre del passaggio elaborato corrente nell&#39;istanza.

Tipo: string

## parentStepName

Nome del passo dell&#39;elemento padre del passaggio corrente.

Tipo: string

## parentTransitionID

ID della transizione che ha portato l’istanza al passaggio elaborato.

Tipo: string

## parentTransitionName

Nome della transizione che ha portato l&#39;istanza al passaggio elaborato.

Tipo: string

## inTest

Indica se il percorso è in modalità di prova o meno.

Tipo: booleano

## processingTime

Quantità totale di tempo in millisecondi dall’entrata del passaggio dell’istanza alla fine dell’elaborazione.

Tipo: long

## instanceType

Indica il tipo di istanza, se è batch o unitario.

Tipo: string

Valori: batch/unitario

## recidivaIndex

Indice della ricorrenza se il percorso è in batch e ricorrente (la prima esecuzione ha ricorrenzaIndex = 1).

Tipo: long

## isBatchToUnitaria

Indica se questa istanza unitaria è stata attivata da un&#39;istanza batch.

Tipo: booleano

## batchExternalKey

Chiave esterna per evento batch.

Tipo: string

## batchInstanceID

questo è l&#39;ID dell&#39;istanza batch.

Tipo: string

## batchUnitarioBranchID

se l&#39;istanza è stata attivata da un&#39;istanza batch, ID ramo unitario.

Tipo: string
