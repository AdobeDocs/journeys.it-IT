---
product: adobe campaign
title: min
description: Informazioni sulla funzione min
feature: Journeys
role: Developer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 7%

---

# min {#min}

Restituisce il valore minimo in un insieme di espressioni, sotto forma di elenco o di due espressioni. I valori Null vengono ignorati.

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
* listDateOnly
* durata
* intero
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

`min(<listDateOnly>)`

Restituisce una data.

`min(<listDecimal>)`

Restituisce un valore decimale.

`min(<decimal>,<decimal>)`

Restituisce un valore decimale.

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
