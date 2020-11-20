---
product: adobe campaign
solution: Journey Orchestration
title: min
description: Ulteriori informazioni sulla funzione min
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

---


# min {#min}

Restituisce il valore minimo tra un insieme di espressioni, dato come un elenco o due espressioni. I valori Null vengono ignorati.

## Categoria

Aggregazione

## Sintassi delle funzioni

`min(<parameters>)`

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

`min(<listDuration>)`

Restituisce una durata.

`min(<listInteger>)`

Restituisce una durata.

`min(<listDateTimeOnly>)`

Restituisce un datetime senza considerare il fuso orario.

`min(<listDateTime>)`

Restituisce un valore datetime.

`min(<listDecimal>)`

Restituisce un valore decimale.

`min(<decimal>,<decimal>)`

Restituisce un valore decimale.

`min(<duration>,<duration>)`

Restituisce una durata.

`min(<dateTime>,<dateTime>)`

Restituisce un valore datetime.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Restituisce un datetime senza considerare il fuso orario.

`min(<integer>,<integer>)`

Restituisce un numero intero.

## Esempi

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

Restituisce 3.

`min([10,null,8])`

Restituisce 8.
