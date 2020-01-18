---
title: max
description: Scopri la funzione max
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---

# max{#max}

Restituisce il valore massimo tra un insieme di espressioni, dato come uno o due espressioni. I valori Null vengono ignorati.

## Categoria

Aggregazione

## Sintassi funzione

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
