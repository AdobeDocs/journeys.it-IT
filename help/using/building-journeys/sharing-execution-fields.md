---
product: adobe campaign
title: Campi di esecuzione dell’azione eventi journeyStep
description: Campi di esecuzione dell’azione eventi journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 4%

---

# Campi di esecuzione dell’azione eventi journeyStep {#sharing-execution-fields}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


Questo mixin verrà condiviso da journeyStepEvent e journeyStepProfileEvent.

Se il passaggio ha un’azione da elaborare, questi campi verranno aggiunti al payload dell’evento.

## actionID

ID dell’azione in esecuzione.

Tipo: stringa

## actionName

Nome dell’azione. Se non è stato impostato alcun nome, verrà utilizzato stepName.

Tipo: stringa

## actionType

Tipo di azione.

Tipo: stringa

## actionParameterized

Indica se l&#39;azione è parametrizzata o meno.

Tipo: booleano

## actionExecutionTime

Tempo (in millisecondi) impiegato per eseguire un&#39;azione corrente.

Tipo: long

## actionExecutionError

Tipo di errore che si verifica quando viene chiamata l’azione.

Tipo: stringa

Valori:
* http
* limiti
* timeout
* errore

## actionExecutionErrorCode

Codice per l’errore di esecuzione dell’azione. Presente se l’errore ha un codice, ad esempio HTTP.

Tipo: stringa

## actionExecutionOriginError

Può verificarsi un timeout in due casi:

* al primo tentativo viene eseguita un’azione. In questo caso, l’esecuzione non è terminata, quindi non si verifica alcun errore sottostante
* in caso di nuovo tentativo: in questo caso, actionExecOrigError/actionExecOrigErrorCode descrive l’errore riscontrato nel tentativo prima del nuovo tentativo.

Ad esempio, viene inviato un messaggio e-mail e al primo tentativo viene restituito un errore HTTP 500. Il recupero viene ritentato, ma la durata dei 2 tentativi supera il timeout. Quindi l’esecuzione dell’azione viene taggata come timeout. La parte azione sarà simile alla seguente:

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

Tipo: stringa

## actionExecutionOriginCode

Codice di errore di actionExecOrigError.

Tipo: stringa

## actionBusinessType

Indica il tipo di azione.

Valori:

* builtin
* E-mail ACS
* SMS ACS
* Push ACS
* cliente
* Epsilon
* ...

Tipo: stringa

## deliveryJobID

Descrive l’ID del processo di consegna per il Percorso batch.

Tipo: stringa

## batchDeliveryID

Descrive l’ID di consegna per il Percorso batch.

Tipo: stringa

## fromSegmentTrigger

Descrive se il Percorso batch viene attivato dal segmento di pubblico.

Tipo: booleano

## actionSchedulerCount

Numero di richieste di notifica del modulo di pianificazione inviate al servizio di pianificazione durante l&#39;elaborazione del passaggio.

Tipo: long
