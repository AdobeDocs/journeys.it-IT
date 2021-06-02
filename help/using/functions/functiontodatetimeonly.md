---
product: adobe campaign
title: toDateTimeOnly
description: Scopri la funzione toDateTime
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 12%

---

# toDateTimeOnly{#toDateTimeOnly}

Converte un valore di argomento in un valore solo di data e ora.

## Categoria

Conversione

## Sintassi della funzione

`toDateTimeOnly(<parameters>)`

## Elemento “parameters”

| Parametro | Tipo |
|-----------|------------------|
| ora in formato ISO-8601 | string |
| ora | dateTime |

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
