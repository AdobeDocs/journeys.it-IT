---
title: inLastHours
description: Scopri la funzione inLastHours
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# inLastHours {#inLastHours}

Restituisce true se l&#39;ora data specificata è compresa tra ora e ora - ore delta.

## Categoria

Data

## Sintassi funzione

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
