---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: Informazioni sulla funzione setDays
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%

---


# setDays {#setDays}

Imposta il giorno solo dell’ora della data o dell’ora della data. Ad esempio, se desiderate aspettare fino a un determinato giorno del mese, potete forzare il giorno.

## Categoria

Data

## Sintassi delle funzioni

`setDays(<parameter>)`

## Parametri

| Parametro | Tipo |
|--- |--- |
| data e ora | dateTime |
| data ora senza considerare il fuso orario | dateTimeOnly |
| giorni | integer |

## Firme e tipo restituito

`setDays(<dateTime>,<days>)`

Restituisce un valore datetime.

`setDays(<dateTimeOnly>,<days>)`

Restituisce un datetime senza considerare il fuso orario.

## Esempi

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Restituisce 2010-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
