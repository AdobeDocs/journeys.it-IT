---
product: adobe campaign
solution: Journey Orchestration
title: inNextYears
description: Scopri la funzione inNextYears
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextYears {#inNextYears}

Restituisce true se una data o un dateTime specificato è compreso tra ora e ora + anni delta.

## Categoria

Data

## Sintassi delle funzioni

`inNextYears(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora | dateTime |
| delta | integer |

## Firme e tipo restituito

`inNextYears(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

Restituisce true.
