---
product: adobe campaign
title: avg
description: Scopri la funzione media
feature: Journeys
role: Developer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 13%

---

# avg {#avg}

Restituisce il valore medio tra un insieme di espressioni, sotto forma di elenco o di due espressioni. I valori Null vengono ignorati.


## Categoria

Aggregazione

## Sintassi della funzione

`avg(<parameter>)`

## Parametri

Tipi supportati:

* listInteger
* listDecimal
* decimale
* intero

## Firme e tipo restituito

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
