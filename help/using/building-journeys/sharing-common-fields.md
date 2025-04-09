---
product: adobe campaign
title: campi comuni degli eventi journeyStep
description: campi comuni degli eventi journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 0%

---

# campi comuni degli eventi journeyStep {#sharing-common-fields}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


Questo mixin verrà condiviso da journeyStepEvent e journeyStepProfileEvent.

Questi sono i campi XDM comuni che [!DNL Journey Orchestration] invia a Adobe Experience Platform. Campi comuni vengono inviati per ogni passaggio elaborato in un percorso. Campi più specifici vengono utilizzati per azioni personalizzate e arricchimenti.

Alcuni di questi campi sono disponibili solo in pattern di elaborazione specifici (esecuzione di azioni, recupero di dati, ecc.) per limitare la dimensione degli eventi.

## entrata

Indica se l&#39;utente è entrato nel percorso. Se non presente, supponiamo che il valore sia falso.

Tipo: booleano

Valori: true/false

## rientro

Indica se l&#39;utente è rientrato nel percorso con la stessa istanza. Se non presente, supponiamo che il valore sia falso.

Tipo: booleano

Valori: true/false

## instanceEnded

Indica se l’istanza è terminata (con successo o meno).

Tipo: booleano

## eventID

ID evento in elaborazione, per il passaggio di elaborazione. Se l&#39;evento è esterno, il valore è il relativo eventId. Se l’evento è interno, il valore è l’eventId interno (ad esempio scheduledNotificationReceived, executeAction, ecc.).

Tipo: stringa

## nodeID

ID del nodo client (dall’area di lavoro).

Tipo: stringa

## stepID

ID univoco del passaggio attualmente in fase di elaborazione.

Tipo: stringa

## stepName

Nome del passaggio attualmente in fase di elaborazione.

Tipo: stringa

## stepType

Tipo del passaggio.

Tipo: stringa

Valori possibili:

* Condizione
* Azione
* Modulo di pianificazione
* Timer

## stepStatus

Stato del passaggio, che rappresenta lo stato del passaggio, al termine dell&#39;elaborazione (e quando l&#39;evento del passaggio viene generato).

Tipo: stringa

Lo stato può essere:

* terminato: il passaggio non presenta alcuna transizione e l’elaborazione è terminata correttamente.
* errore: l’elaborazione del passaggio ha generato un errore.
* transizioni: il passaggio è in attesa che un evento passi a un altro passaggio.
* limitato: il passaggio non è riuscito a causa di un errore di limite, generato durante un’azione o un arricchimento.
* timeout: il passaggio non è riuscito a causa di un errore di timeout, generato durante un&#39;azione o un arricchimento.
* instanceTimedout: l&#39;elaborazione del passaggio è stata interrotta perché è stato raggiunto il timeout dell&#39;istanza.

## journeyID

ID del percorso.

Tipo: stringa

## journeyVersionID

ID della versione del percorso. Questo ID rappresenta il riferimento di identità al percorso, nel caso di journeyStepEvent.

Tipo: stringa

## journeyVersionName

Nome della versione del percorso.

Tipo: stringa

## journeyVersion

Versione del percorso.

Tipo: stringa

## instanceID

ID interno dell’istanza di percorso.

Tipo: stringa

## externalKey

Chiave esterna estratta dall’evento per elaborarlo.

Tipo: stringa

## parentStepID

ID del passaggio padre del passaggio elaborato corrente nell’istanza.

Tipo: stringa

## parentStepName

Nome del passaggio padre del passaggio corrente.

Tipo: stringa

## parentTransitionID

ID della transizione che ha portato l’istanza al passaggio elaborato.

Tipo: stringa

## parentTransitionName

Nome della transizione che ha portato l’istanza al passaggio elaborato.

Tipo: stringa

## inTest

Indica se il percorso è in modalità di test o meno.

Tipo: booleano

## processingTime

Tempo totale in millisecondi dall’ingresso del passaggio dell’istanza alla fine dell’elaborazione.

Tipo: long

## instanceType

Indica il tipo di istanza, se è batch o unitaria.

Tipo: stringa

Valori: batch/unitario

## recurrenceIndex

Indice della ricorrenza se il percorso è batch e ricorrente (la prima esecuzione ha recurrenceIndex = 1).

Tipo: long

## isBatchToUninary

Indica se questa istanza unitaria è stata attivata da un&#39;istanza batch.

Tipo: booleano

## batchExternalKey

Chiave esterna per evento batch.

Tipo: stringa

## batchInstanceID

questo è l’ID dell’istanza batch.

Tipo: stringa

## batchUninaryBranchID

se l’istanza è stata attivata da un’istanza batch, ID del ramo unitario.

Tipo: stringa
