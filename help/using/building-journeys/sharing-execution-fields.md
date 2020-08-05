---
title: Campi di esecuzione azione degli eventi journeyStep
description: Campi di esecuzione azione degli eventi journeyStep
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 10402a774bda66629f30869102d5e6ceca267535
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 4%

---


# Campi di esecuzione azione degli eventi journeyStep {#sharing-execution-fields}

Questo mixin sarà condiviso da pathStepEvent e pathStepProfileEvent.

Se il passaggio dispone di un&#39;azione da elaborare, tali campi saranno aggiunti al payload dell&#39;evento.

## actionID

ID dell’azione che viene eseguita.

Tipo: string

## actionName

Nome dell’azione. Se non è stato impostato alcun nome, stepName verrà eseguito.

Tipo: string

## actionType

Tipo di azione.

Tipo: string

## actionParameterized

Indica se l&#39;azione è parametrizzata o meno.

Tipo: boolean

## actionExecutionTime

Il tempo (in millisecondi) impiegato per eseguire un&#39;azione corrente.

Tipo: long

## actionExecutionError

Tipo di errore che si verifica quando l’azione viene chiamata.

Tipo: string

Valori:
* http
* tappatura
* timeout
* error

## actionExecutionErrorCode

Errore di codice per l&#39;esecuzione dell&#39;azione. Presente se l&#39;errore ha un codice, ad esempio HTTP uno.

Tipo: string

## actionExecutionOriginError

Un timeout può verificarsi, in due casi:

* al primo tentativo viene eseguita un&#39;azione. In questo caso, l&#39;esecuzione non è completata, quindi non vi è alcun errore sottostante
* in caso di nuovo tentativo: in questo caso, actionExecOrigError/actionExecOrigErrorCode descrive l&#39;errore rilevato nel tentativo prima del tentativo.

Ad esempio, viene inviato un messaggio e-mail e al primo tentativo viene restituito un errore HTTP 500. Il recupero viene ritentato, ma la durata dei 2 tentativi supera il timeout. Quindi l&#39;esecuzione dell&#39;azione viene taggata come timeout. La parte di azione avrà l&#39;aspetto seguente:

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

Codice di errore di actionExecOrigError.

Tipo: string

## actionBusinessType

Indica il tipo di azione.

Valori:

* builtin
* Email ACS
* ACS SMS
* ACS Push
* cliente
* Epsilon
* ...

Tipo: string

## deliveryJobID

Questo descrive l&#39;ID del processo di consegna per il batch Journey.

Tipo: string

## batchDeliveryID

Questo descrive l&#39;ID consegna per il batch Journey.

Tipo: string

## fromSegmentTrigger

Indica se il percorso batch viene attivato dal segmento di pubblico.

Tipo: boolean

## actionSchedulerCount

Conteggio delle richieste di notifica del pianificatore inviate al servizio pianificatore durante l&#39;elaborazione dei passaggi.

Tipo: long
