---
product: adobe campaign
title: sum
description: Informazioni sulla somma delle funzioni
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 13%

---

# sum {#sum}

Restituisce la somma dei valori di un insieme di espressioni. I valori Null vengono ignorati.

## Categoria

Aggregazione

## Sintassi della funzione

`sum(<parameters>)`

## Elemento “parameters”

* listInteger
* listDecimal
* durata
* intero
* decimale

## Firme e tipi restituiti

`sum(<listDecimal>)`

Restituisce un valore decimale.

`sum(<listInteger>)`

Restituisce un numero intero.

`sum(<integer>,<integer>)`

Restituisce un numero intero.

`sum(<decimal>,<decimal>)`

Restituisce un valore decimale.

## Esempi

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

Restituisce 21.

`sum([10.5,null,8.1])`

Restituisce 18,6.
