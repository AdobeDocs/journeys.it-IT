---
product: adobe campaign
solution: Journey Orchestration
title: Campi di esecuzione azione degli eventi journeyStep
description: Campi di esecuzione azione degli eventi journeyStep
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 4%

---


# Campi di esecuzione azione degli eventi journeyStep {#sharing-execution-fields}

Questo mixin sarà condiviso da journeyStepEvent e journeyStepProfileEvent.

Se il passaggio dispone di un’azione da elaborare, tali campi verranno aggiunti al payload dell’evento.

## actionID

ID dell&#39;azione in corso di esecuzione.

Tipo: string

## actionName

Nome dell’azione. Se non è stato impostato alcun nome, viene eseguito stepName.

Tipo: string

## actionType

Tipo di azione.

Tipo: string

## actionParameter

Indica se l’azione è parametrizzata o meno.

Tipo: booleano

## actionExecutionTime

Il tempo (in millisecondi) impiegato per eseguire un&#39;azione corrente.

Tipo: long

## actionExecutionError

Tipo di errore che si verifica quando viene chiamata l&#39;azione.

Tipo: string

Valori:
* http
* tappatura
* timeout
* errore

## actionExecutionErrorCode

Errore di esecuzione del codice per l&#39;azione. Presente se l&#39;errore ha un codice, ad esempio uno HTTP.

Tipo: string

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

Tipo: string

## actionExecutionOriginCode

Codice di errore dell&#39;actionExecOrigError.

Tipo: string

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

Tipo: string

## deliveryJobID

Questo descrive l’ID del processo di consegna per il Percorso batch.

Tipo: string

## batchDeliveryID

Questo descrive l’ID di consegna per il Percorso batch.

Tipo: string

## fromSegmentTrigger

Questo descrive se il Percorso batch viene attivato dal segmento di pubblico.

Tipo: booleano

## actionSchedulerCount

Numero di richieste di notifica del programmatore inviate al servizio di pianificazione durante l&#39;elaborazione dei passaggi.

Tipo: long
