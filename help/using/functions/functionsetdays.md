---
product: adobe campaign
title: setDays
description: Scopri la funzione setDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 13%

---

# setDays {#setDays}

Imposta solo il giorno di un&#39;ora o di una data. Ad esempio, se desideri attendere fino a un determinato giorno del mese, puoi forzare il giorno.

## Categoria

Data

## Sintassi della funzione

`setDays(<parameter>)`

## Elemento “parameters”

| Parametro | Tipo |
|--- |--- |
| data e ora | dateTime |
| data e ora senza considerare il fuso orario | dateTimeOnly |
| giorni | intero |

## Firme e tipo restituito

`setDays(<dateTime>,<days>)`

Restituisce un valore datetime.

`setDays(<dateTimeOnly>,<days>)`

Restituisce un valore datetime senza considerare il fuso orario.

## Esempi

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Restituisce 2010-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
