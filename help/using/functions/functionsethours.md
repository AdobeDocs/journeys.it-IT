---
product: adobe campaign
title: setHours
description: Scopri la funzione setHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 9%

---

# setHours {#setHours}

Imposta solo le ore di una data/ora o data/ora. Ad esempio, se desideri aspettare fino a un’ora specifica domani, puoi forzare l’ora.

## Categoria

Data

## Sintassi della funzione

`setHours(<parameter>)`

## Parametri

| Parametro | Tipo |
|--- |--- |
| data e ora | dateTime |
| data e ora senza considerare il fuso orario | dateTimeOnly |
| ore | numero intero |

## Firme e tipo restituito

`setHours(<dateTime>,<hours>)`

Restituisce un valore datetime.

`setHours(<dateTimeOnly>,<hours>)`

Restituisce un valore datetime senza considerare il fuso orario.

## Esempi

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Restituisce 2010-12-12T04:11:00Z

`setHours(nowWithDelta(1, "days"), 20)`

Restituisce domani alle 20:XY, dove XY corrisponde ai minuti al momento della valutazione dell&#39;ora corrente. Se la valutazione viene eseguita alle 02:45, l’ora restituita sarà le 20:45.
