---
product: adobe campaign
solution: Journey Orchestration
title: max
description: Scopri la funzione max
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

---

# max{#max}

Restituisce il valore massimo tra un insieme di espressioni, dato come uno o due espressioni. I valori Null vengono ignorati.

## Categoria

Aggregazione

## Sintassi delle funzioni

`max(<parameter>)`

## Parametri

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* length
* integer
* decimal
* dateTime
* dateTimeOnly

## Firme e tipi restituiti

`max(<listDuration>)`

Restituisce una durata.

`max(<listInteger>)`

Restituisce una durata.

`max(<listDateTimeOnly>)`

Restituisce un datetime senza considerare il fuso orario.

`max(<listDateTime>)`

Restituisce un valore datetime.

`max(<listDecimal>)`

Restituisce un valore decimale.

`max(<decimal>,<decimal>)`

Restituisce un valore decimale.

`max(<duration>,<duration>)`

Restituisce una durata.

`max(<dateTime>,<dateTime>)`

Restituisce un valore datetime.

`max(<dateTimeOnly>,<dateTimeOnly>)`

Restituisce un datetime senza considerare il fuso orario.

`max(<integer>,<integer>)`

Restituisce un numero intero.

## Esempi

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

Restituisce 10.

`max([10,null,8])`

Restituisce 10.
