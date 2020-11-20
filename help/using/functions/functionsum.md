---
product: adobe campaign
solution: Journey Orchestration
title: sum
description: Scopri la somma delle funzioni
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 7%

---


# sum {#sum}

Restituisce la somma dei valori di un insieme di espressioni. I valori Null vengono ignorati.

## Categoria

Aggregazione

## Sintassi delle funzioni

`sum(<parameters>)`

## Parametri

* listInteger
* listDecimal
* length
* integer
* decimal

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
