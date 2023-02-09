---
product: adobe campaign
title: avg
description: Scopri l’avg della funzione
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 16%

---

# avg {#avg}

Restituisce il valore medio tra un insieme di espressioni, dato come elenco o due espressioni. I valori Null vengono ignorati.


## Categoria

Aggregazione

## Sintassi della funzione

`avg(<parameter>)`

## Parametri

Tipi supportati:

* listInteger
* listDecimal
* decimal
* numero intero

## Firme e tipo restituito

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

Restituisce un decimale.

## Esempi

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

Restituisce 7,0.

`avg(10.2, 3)`

Restituisce 6.6.
