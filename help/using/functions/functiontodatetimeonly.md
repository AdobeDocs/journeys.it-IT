---
product: adobe campaign
title: toDateTimeOnly
description: Scopri la funzione toDateTime
feature: Journeys
role: Developer
level: Experienced
exl-id: b19adbd0-8449-4bd4-bc4d-f1f305f87cb0
source-git-commit: 58514d6757f9705f5baa71cfbbe0bdfe65c8e16c
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%

---

# toDateTimeOnly{#toDateTimeOnly}

Converte un valore di argomento in un valore di sola data e ora.

## Categoria

Conversione

## Sintassi della funzione

`toDateTimeOnly(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora in formato ISO-8601 o &quot;AAAA-MM-GG&quot; (formato data XDM) | stringa |
| data e ora | dateTime |

## Firme e tipi restituiti

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--
`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`
-->

Restituisce un valore datetime senza considerare il fuso orario.

## Esempi

`toDateTimeOnly ("2016-08-18")`

restituisce un valore dateTime che rappresenta 2016-08-18T00:00:00.000

`toDateTimeOnly(now())`

<!--
`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.
-->
