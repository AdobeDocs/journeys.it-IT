---
product: adobe campaign
title: inNextYears
description: Scopri la funzione inNextYears
feature: Journeys
role: Developer
level: Experienced
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextYears {#inNextYears}

Restituisce true se una data o un&#39;ora specificata è compresa tra now e now + delta anni.

## Categoria

Data

## Sintassi della funzione

`inNextYears(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora | dateTime |
| delta | intero |

## Firme e tipo restituito

`inNextYears(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

Restituisce true.
