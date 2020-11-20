---
product: adobe campaign
solution: Journey Orchestration
title: avg
description: Ulteriori informazioni sulla funzione avg
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 8%

---


# avg {#avg}

Restituisce il valore medio tra un insieme di espressioni, dato come un elenco o due espressioni. I valori Null vengono ignorati.


## Categoria

Aggregazione

## Sintassi delle funzioni

`avg(<parameter>)`

## Parametri

Tipi supportati:

* listInteger
* listDecimal
* decimal
* integer

## Firme e tipo restituito

`avg(<listInteger>)`

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

Restituisce un valore decimale.

## Esempi

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

Restituisce 7,0.

`avg(10.2, 3)`

Restituisce 6,6.
