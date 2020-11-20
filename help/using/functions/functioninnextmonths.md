---
product: adobe campaign
solution: Journey Orchestration
title: inNextMonths
description: Scopri la funzione inNextMonths
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextMonths {#inNextMonths}

Restituisce true se una data o un dateTime specificato è compreso tra ora e ora + mesi delta.

## Categoria

Data

## Sintassi delle funzioni

`inNextMonths(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora | dateTime |
| delta | integer |

## Firme e tipo restituito

`inNextMonths(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

Restituisce true.
