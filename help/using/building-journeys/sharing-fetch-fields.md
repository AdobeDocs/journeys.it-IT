---
product: adobe campaign
title: Campi di recupero dati di eventi journeyStep
description: Campi di recupero dati di eventi journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 7%

---

# Campi di recupero dati di eventi journeyStep {#sharing-fetch-fields}

Questo mixin verrà condiviso da journeyStepEvent e journeyStepProfileEvent.

Durante un passaggio di elaborazione, possiamo avere N recupero dati sui gruppi di campi.

## fetchTotalTime

Tempo totale impiegato per il recupero dei dati in millisecondi durante l’elaborazione del passaggio.

Tipo: long

## fetchTypeInError

Definisce se il recupero in errore si trova su Adobe Experience Platform o su un’origine dati personalizzata.

Tipo: stringa

Valori:
* aep
* personalizzato

## fetchError

Tipo di errore che si verifica quando viene elaborato il recupero dei dati.

Tipo: stringa

Valori:
* http
* limite
* timeout
* error

## fetchErrorCode

Codice per l’errore di recupero. Presente se l’errore ha un codice, ad esempio HTTP. Ad esempio, se actionExecError è http, il codice 404 rappresenta l&#39;errore HTTP 404.

Tipo: stringa

## fetchOriginError

Può verificarsi un timeout in due casi:

* al primo tentativo l’azione viene eseguita. In questo caso, l’esecuzione non è terminata, quindi non si verifica alcun errore sottostante
* in caso di nuovo tentativo: in questo caso, actionExecOrigError/actionExecOrigErrorCode descrive l’errore riscontrato nel tentativo prima del nuovo tentativo.

Ad esempio, i dati vengono recuperati da Unified Profile Service e al primo tentativo viene restituito un errore HTTP 500. Il recupero viene ritentato, ma la durata dei 2 tentativi supera il timeout. Quindi l’esecuzione dell’azione viene taggata come timeout. La parte azione sarà simile alla seguente:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Tipo: stringa

## fetchOriginErrorCode

Il codice di errore fornito dal sistema [!DNL Journey Orchestration] sta eseguendo una query. Ad esempio, può essere un 404, 500, ecc.

Tipo: stringa

## fetchCount

Quante volte vengono recuperati i dati, indipendentemente dal tipo di origine.

Tipo: long

## fetchPlatformTotalTime

Il tempo totale impiegato per recuperare i dati da Adobe Experience Platform in millisecondi. Nota: questo periodo di tempo viene calcolato dal momento in cui il motore invia l’evento di arricchimento al servizio di arricchimento e riceve la risposta.

Tipo: long

## fetchPlatformCount

Quante volte i dati vengono recuperati da Adobe Experience Platform.

Tipo: long

## fetchCustomTotalTime

Tempo di recupero dei dati personalizzati in millisecondi. Nota: questo periodo di tempo viene calcolato dal momento in cui il motore invia l’evento di arricchimento al servizio di arricchimento e riceve la risposta

Tipo: long

## fetchCustomCount

Quante volte i dati personalizzati vengono recuperati da sistemi esterni.

Tipo: long
