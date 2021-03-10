---
product: adobe campaign
solution: Journey Orchestration
title: min
description: Informazioni sulla funzione min
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 5%

---


# min {#min}

Restituisce il valore minimo tra un set di espressioni, dato come elenco o due espressioni. I valori Null vengono ignorati.

## Categoria

Aggregazione

## Sintassi della funzione

`min(<parameters>)`

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

`min(<listDuration>)`

Restituisce una durata.

`min(<listInteger>)`

Restituisce una durata.

`min(<listDateTimeOnly>)`

Restituisce un valore datetime senza considerare il fuso orario.

`min(<listDateTime>)`

Restituisce un valore datetime.

`min(<listDecimal>)`

Restituisce un decimale.

`min(<decimal>,<decimal>)`

Restituisce un decimale.

`min(<duration>,<duration>)`

Restituisce una durata.

`min(<dateTime>,<dateTime>)`

Restituisce un valore datetime.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Restituisce un valore datetime senza considerare il fuso orario.

`min(<integer>,<integer>)`

Restituisce un numero intero.

## Esempi

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

Restituisce 3.

`min([10,null,8])`

Restituisce 8.
