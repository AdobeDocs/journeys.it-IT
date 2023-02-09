---
product: adobe campaign
title: Campi di esecuzione dell’azione eventi journeyStep
description: Campi di esecuzione dell’azione eventi journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 12%

---

# Campi di esecuzione dell’azione eventi journeyStep {#sharing-execution-fields}

Questo mixin sarà condiviso da journeyStepEvent e journeyStepProfileEvent.

Se il passaggio dispone di un’azione da elaborare, tali campi verranno aggiunti al payload dell’evento.

## actionID

ID dell&#39;azione in corso di esecuzione.

Tipo: stringa

## actionName

Nome dell’azione. Se non è stato impostato alcun nome, viene eseguito stepName.

Tipo: stringa

## actionType

Tipo di azione.

Tipo: stringa

## actionParameter

Indica se l’azione è parametrizzata o meno.

Tipo: booleano

## actionExecutionTime

Il tempo (in millisecondi) impiegato per eseguire un&#39;azione corrente.

Tipo: long

## actionExecutionError

Tipo di errore che si verifica quando viene chiamata l&#39;azione.

Tipo: stringa

Valori:
* http
* tappatura
* timeout
* error

## actionExecutionErrorCode

Errore di esecuzione del codice per l&#39;azione. Presente se l&#39;errore ha un codice, ad esempio uno HTTP.

Tipo: stringa

## actionExecutionOriginError

Può verificarsi un timeout, in due casi:

* al primo tentativo viene eseguita un&#39;azione. In questo caso, l&#39;esecuzione non è completata, quindi non vi è alcun errore sottostante
* in un nuovo tentativo: in questo caso, actionExecOrigError/actionExecOrigErrorCode descrive l&#39;errore rilevato nel tentativo prima del nuovo tentativo.

Ad esempio, viene inviata un’e-mail e al primo tentativo viene restituito un errore HTTP 500. Il recupero viene ritentato, ma la durata dei 2 tentativi supera il timeout. Quindi l’esecuzione dell’azione viene taggata come timeout. La parte azione avrà un aspetto simile al seguente:

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

Codice di errore dell&#39;actionExecOrigError.

Tipo: stringa

## actionBusinessType

Indica il tipo di azione.

Valori:

* costruzione
* E-mail ACS
* SMS ACS
* Push ACS
* cliente
* Epsilon
* ...

Tipo: stringa

## deliveryJobID

Questo descrive l’ID del processo di consegna per il Percorso batch.

Tipo: stringa

## batchDeliveryID

Questo descrive l’ID di consegna per il Percorso batch.

Tipo: stringa

## fromSegmentTrigger

Questo descrive se il Percorso batch viene attivato dal segmento di pubblico.

Tipo: booleano

## actionSchedulerCount

Numero di richieste di notifica del programmatore inviate al servizio di pianificazione durante l&#39;elaborazione dei passaggi.

Tipo: long
