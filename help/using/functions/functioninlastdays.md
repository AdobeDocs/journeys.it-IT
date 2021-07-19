---
product: adobe campaign
title: inLastDays
description: Scopri la funzione inLastDays
feature: Percorsi
role: Data Engineer
level: Experienced
exl-id: 1fc29153-3554-4af1-bb2e-7bba53ffce69
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inLastDays {#inLastDays}

Restituisce true se una data o un valore dateTime specificato è compreso tra ora e ora - giorni delta.

## Categoria

Data

## Sintassi della funzione

`inLastDays(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| ora | dateTime |
| delta | integer |

## Firme e tipo restituito

`inLastDays(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

Restituisce true.
