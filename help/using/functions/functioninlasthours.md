---
product: adobe campaign
solution: Journey Orchestration
title: inLastHours
description: Scopri la funzione inLastHours
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 8%

---


# inLastHours {#inLastHours}

Restituisce true se l&#39;ora data specificata è compresa tra ora e ora - ore delta.

## Categoria

Data

## Sintassi delle funzioni

`inLastHours(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora | dateTime |
| delta | integer |

## Firme e tipo restituito

`inLastHours(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

Restituisce true.

`inLastHours(@{MyEvent.timestamp}, 4)`

Restituisce true.
