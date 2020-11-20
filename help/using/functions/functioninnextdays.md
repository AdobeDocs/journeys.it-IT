---
product: adobe campaign
solution: Journey Orchestration
title: inNextDays
description: Scopri la funzione inNextDays
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextDays {#inNextDays}

Restituisce true se una data o un dateTime specificato è compreso tra ora e ora + giorni delta.

## Categoria

Data

## Sintassi delle funzioni

`inNextDays(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora | dateTime |
| delta | integer |

## Firme e tipo restituito

`inNextDays(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Restituisce true.
