---
product: adobe campaign
title: inNextDays
description: Scopri la funzione inNextDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 13%

---

# inNextDays {#inNextDays}

Restituisce true se una data o un valore dateTime specificato è compreso tra ora e ora + giorni delta.

## Categoria

Data

## Sintassi della funzione

`inNextDays(<dateTime>,<delta>)`

## Elemento “parameters”

| Parametro | Tipo |
|-----------|------------------|
| ora | dateTime |
| delta | integer |

## Firme e tipo restituito

`inNextDays(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Restituisce true.
