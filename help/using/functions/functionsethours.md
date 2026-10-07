---
product: adobe campaign
title: setHours
description: Scopri la funzione setHours
feature: Journeys
role: Developer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '106'
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
| ore | intero |

## Firme e tipo restituito

`setHours(<dateTime>,<hours>)`

Restituisce un valore datetime.

`setHours(<dateTimeOnly>,<hours>)`

Restituisce un valore datetime senza considerare il fuso orario.

## Esempi

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Restituisce 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Restituisce domani alle 20.00, dove XY corrisponde ai minuti al momento della valutazione dell&#39;ora corrente. :XYSe la valutazione viene eseguita alle 02:45, l’ora restituita sarà le 20:45.
