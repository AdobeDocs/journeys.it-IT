---
product: adobe campaign
title: inNextMonths
description: Scopri la funzione inNextMonths
feature: Journeys
role: Developer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextMonths {#inNextMonths}

Restituisce true se una data o un&#39;ora specificata è compresa tra now e now + delta mesi.

## Categoria

Data

## Sintassi della funzione

`inNextMonths(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora | dateTime |
| delta | intero |

## Firme e tipo restituito

`inNextMonths(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

Restituisce true.
