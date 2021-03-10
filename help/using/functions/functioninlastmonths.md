---
product: adobe campaign
solution: Journey Orchestration
title: inLastMonths
description: Scopri la funzione inLastMonths
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inLastMonths {#inLastMonths}

Restituisce true se una data o un&#39;ora specificata è compresa tra ora e ora - mesi delta.

## Categoria

Data

## Sintassi della funzione

`inLastMonths(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| ora | dateTime |
| delta | integer |

## Firme e tipo restituito

`inLastMonths(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4))`

Restituisce true.
