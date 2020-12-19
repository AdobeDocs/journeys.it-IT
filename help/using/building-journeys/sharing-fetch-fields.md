---
product: adobe campaign
solution: Journey Orchestration
title: Campi di recupero dati di journeyStep
description: Campi di recupero dati di journeyStep
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 4%

---


# Campi di recupero dati di journeyStep {#sharing-fetch-fields}

Questo mixin sarà condiviso da pathStepEvent e pathStepProfileEvent.

Durante un&#39;elaborazione passo, è possibile ottenere N dati sui gruppi di campi.

## fetchTotalTime

Quantità totale di tempo trascorso nel recupero dei dati in millisecondi durante l&#39;elaborazione dei passaggi.

Tipo: long

## fetchTypeInError

Definisce se l&#39;errore di recupero si trova sull&#39;Adobe Experience Platform o su un&#39;origine dati personalizzata.

Tipo: string

Valori:
* aep
* custom

## fetchError

Tipo di errore che si verifica quando viene elaborato il recupero dei dati.

Tipo: string

Valori:
* http
* tappatura
* timeout
* error

## fetchErrorCode

Codice per errore di recupero. Presente se l&#39;errore ha un codice, ad esempio HTTP uno. Ad esempio, se actionExecError è http, il codice 404 rappresenta l&#39;errore HTTP 404.

Tipo: string

## fetchOriginError

Un timeout può verificarsi, in due casi:

* al primo tentativo l’azione viene eseguita. In questo caso, l&#39;esecuzione non è completata, quindi non vi è alcun errore sottostante
* in caso di nuovo tentativo: in questo caso, actionExecOrigError/actionExecOrigErrorCode descrive l&#39;errore rilevato nel tentativo prima del tentativo.

Ad esempio, i dati vengono recuperati da Unified Profile Service e al primo tentativo viene restituito un errore HTTP 500. Il recupero viene ritentato, ma la durata dei 2 tentativi supera il timeout. Quindi l&#39;esecuzione dell&#39;azione viene taggata come timeout. La parte di azione avrà l&#39;aspetto seguente:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Tipo: string

## fetchOriginErrorCode

Il codice di errore fornito dal sistema [!DNL Journey Orchestration] sta eseguendo query. Ad esempio, può essere un 404, 500, ecc.

Tipo: string

## fetchCount

Quante volte i dati vengono recuperati, indipendentemente dal tipo di origine.

Tipo: long

## fetchPlatformTotalTime

Il tempo totale impiegato per recuperare i dati da Adobe Experience Platform in millisecondi. Nota: questo tempo viene calcolato dal momento in cui il motore invia l’evento di arricchimento al servizio di arricchimento e riceve la risposta.

Tipo: long

## fetchPlatformCount

Quante volte i dati vengono recuperati da Adobe Experience Platform.

Tipo: long

## fetchCustomTotalTime

Quantità di tempo per recuperare i dati personalizzati in millisecondi. Nota: questo tempo viene calcolato dal momento in cui il motore invia l’evento di arricchimento al servizio di arricchimento e riceve la risposta

Tipo: long

## fetchCustomCount

Quante volte i dati personalizzati vengono recuperati da sistemi esterni.

Tipo: long
