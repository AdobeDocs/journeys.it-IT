---
title: setDays
description: Informazioni sulla funzione setDays
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# setDays {#setDays}

Imposta il giorno solo dell’ora della data o dell’ora della data. Ad esempio, se desiderate aspettare fino a un determinato giorno del mese, potete forzare il giorno.

## Categoria

Data

## Sintassi funzione

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
