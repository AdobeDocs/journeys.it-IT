---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: Informazioni sulla funzione setHours
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 5%

---


# setHours {#setHours}

Imposta le ore solo per l’ora o l’ora della data. Ad esempio, se si desidera aspettare fino a una certa ora domani, è possibile forzare l&#39;ora.

## Categoria

Data

## Sintassi delle funzioni

`setHours(<parameter>)`

## Parametri

| Parametro | Tipo |
|--- |--- |
| data e ora | dateTime |
| data ora senza considerare il fuso orario | dateTimeOnly |
| ore | integer |

## Firme e tipo restituito

`setHours(<dateTime>,<hours>)`

Restituisce un valore datetime.

`setHours(<dateTimeOnly>,<hours>)`

Restituisce un datetime senza considerare il fuso orario.

## Esempi

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Restituisce 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Ritorna domani alle 20.
