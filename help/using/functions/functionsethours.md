---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: Scopri la funzione setHours
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 6%

---


# setHours {#setHours}

Imposta solo le ore di un’ora di data o di data. Ad esempio, se desideri aspettare fino a una certa ora domani, puoi forzare l’ora.

## Categoria

Data

## Sintassi della funzione

`setHours(<parameter>)`

## Parametri

| Parametro | Tipo |
|--- |--- |
| ora | dateTime |
| data e ora senza considerare il fuso orario | dateTimeOnly |
| ore | integer |

## Firme e tipo restituito

`setHours(<dateTime>,<hours>)`

Restituisce un valore datetime.

`setHours(<dateTimeOnly>,<hours>)`

Restituisce un valore datetime senza considerare il fuso orario.

## Esempi

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Restituisce 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Torna domani alle 20.
