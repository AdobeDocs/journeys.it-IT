---
product: adobe campaign
title: inLastDays
description: Scopri la funzione inLastDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1fc29153-3554-4af1-bb2e-7bba53ffce69
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastDays {#inLastDays}

Restituisce true se una data o un valore dateTime specificato è compreso tra now e now - delta days.

## Categoria

Data

## Sintassi della funzione

`inLastDays(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora | dateTime |
| delta | numero intero |

## Firme e tipo restituito

`inLastDays(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4)`

Restituisce true.
