---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: Scopri la funzione setDays
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 6%

---


# setDays {#setDays}

Imposta solo il giorno dell’ora o dell’ora della data. Ad esempio, se desideri attendere fino a un determinato giorno del mese, puoi forzare il giorno .

## Categoria

Data

## Sintassi della funzione

`setDays(<parameter>)`

## Parametri

| Parametro | Tipo |
|--- |--- |
| ora | dateTime |
| data e ora senza considerare il fuso orario | dateTimeOnly |
| giorni | integer |

## Firme e tipo restituito

`setDays(<dateTime>,<days>)`

Restituisce un valore datetime.

`setDays(<dateTimeOnly>,<days>)`

Restituisce un valore datetime senza considerare il fuso orario.

## Esempi

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Restituisce 2010-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
