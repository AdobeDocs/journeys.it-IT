---
product: adobe campaign
solution: Journey Orchestration
title: toDateTimeOnly
description: Scopri la funzione toDateTime
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 8%

---


# toDateTimeOnly{#toDateTimeOnly}

Converte un valore argomento in un valore solo per l&#39;ora della data.

## Categoria

Conversione

## Sintassi delle funzioni

`toDateTimeOnly(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora in formato ISO-8601 | string |
| data e ora | dateTime |

## Firme e tipi restituiti

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Restituisce un datetime senza considerare il fuso orario.

## Esempi

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

Restituisce 2016-08-18T23:17:59.123.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
