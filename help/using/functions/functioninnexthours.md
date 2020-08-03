---
title: inNextHours
description: Scopri la funzione inNextHours
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
source-git-commit: 0e06abf518445ce145d2d042b16daaa2dfd9603e
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextHours {#inNextHours}

Restituisce true se una data o un dateTime specificato è compreso tra ora e ora + ore delta.

## Categoria

Data

## Sintassi delle funzioni

`inNextHours(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora | dateTime |
| delta | integer |

## Firme e tipo restituito

`inNextHours(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Restituisce true.
