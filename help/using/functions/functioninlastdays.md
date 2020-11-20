---
product: adobe campaign
solution: Journey Orchestration
title: inLastDays
description: Scopri la funzione inLastDays
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inLastDays {#inLastDays}

Restituisce true se una data o un dateTime specificato è compreso tra ora e ora - giorni delta.

## Categoria

Data

## Sintassi delle funzioni

`inLastDays(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora | dateTime |
| delta | integer |

## Firme e tipo restituito

`inLastDays(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

Restituisce true.
