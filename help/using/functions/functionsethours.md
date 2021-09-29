---
product: adobe campaign
title: setHours
description: Scopri la funzione setHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 51536b20e81cde1a7fdd7f4654d70bfe6176b0d4
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 8%

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

Restituisce domani alle 8:XY PM, XY indica i minuti al momento della valutazione dell&#39;ora corrente. Se la valutazione avviene alle 2:45 del mattino, il tempo restituito sarà alle 8:45 del pomeriggio.
