---
product: adobe campaign
title: toDateTimeOnly
description: Scopri la funzione toDateTime
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b19adbd0-8449-4bd4-bc4d-f1f305f87cb0
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 16%

---

# toDateTimeOnly{#toDateTimeOnly}

Converte un valore di argomento in un valore solo di data e ora.

## Categoria

Conversione

## Sintassi della funzione

`toDateTimeOnly(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| ora in formato ISO-8601 o &quot;AAAA-MM-GG&quot; (formato XDM Data) | string |
| ora | dateTime |

## Firme e tipi restituiti

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Restituisce un datetime senza considerare il fuso orario.

## Esempi

`toDateTimeOnly ("2016-08-18")`

restituisce un dateTime che rappresenta 2016-08-18T00:00:00,000

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
