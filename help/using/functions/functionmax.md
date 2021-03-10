---
product: adobe campaign
solution: Journey Orchestration
title: max
description: Scopri la funzione max
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 5%

---

# max{#max}

Restituisce il valore massimo tra un set di espressioni, dato come elenco o due espressioni. I valori Null vengono ignorati.

## Categoria

Aggregazione

## Sintassi della funzione

`max(<parameter>)`

## Parametri

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* durata
* integer
* decimale
* dateTime
* dateTimeOnly

## Firme e tipi restituiti

`max(<listDuration>)`

Restituisce una durata.

`max(<listInteger>)`

Restituisce una durata.

`max(<listDateTimeOnly>)`

Restituisce un valore datetime senza considerare il fuso orario.

`max(<listDateTime>)`

Restituisce un valore datetime.

`max(<listDecimal>)`

Restituisce un decimale.

`max(<decimal>,<decimal>)`

Restituisce un decimale.

`max(<duration>,<duration>)`

Restituisce una durata.

`max(<dateTime>,<dateTime>)`

Restituisce un valore datetime.

`max(<dateTimeOnly>,<dateTimeOnly>)`

Restituisce un valore datetime senza considerare il fuso orario.

`max(<integer>,<integer>)`

Restituisce un numero intero.

## Esempi

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

Restituisce 10.

`max([10,null,8])`

Restituisce 10.
