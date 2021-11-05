---
product: adobe campaign
title: sort
description: Scopri l’ordinamento delle funzioni
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 18%

---

# sort {#sort}

Ordina un elenco di valori nell’ordine naturale. Il primo argomento è l’elenco dei valori, il secondo è un valore booleano che indica se l’ordinamento è crescente (true) o decrescente (false).

## Categoria

Elenco

## Sintassi della funzione

`sort(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| Elenco | listString |
| Elenco | listBoolean |
| Elenco | listInteger |
| Elenco | listDecimal |
| Elenco | listDuration |
| Elenco | listDateTime |
| Elenco | listDateTimeOnly |
| Elenco | listDateOnly |
| Booleano | Booleano |

## Firma e tipo restituito

`sort(<listInteger>,<boolean>)`

Restituisce un elenco di numeri interi.

`sort(<listDecimal>,<boolean>)`

Restituisce un elenco di decimali.

`sort(<listString>,<boolean>)`

Restituisce un elenco di stringhe.

`sort(<listDateTimeOnly>,<boolean>)`

Restituisce un elenco di date senza considerare il fuso orario.

`sort(<listDateTime>,<boolean>)`

Restituisce un elenco di date.

`sort(<listDateOnly>,<boolean>)`

Restituisce un elenco di date.

`sort(<listBoolean>,<boolean>)`

Restituisce un elenco di booleani.

## Esempio

`sort(["A", "C", "B"], true)`

Restituisce `["A","B","C"]`.

`sort([1, 3, 2], false)`

Restituisce `[3, 2, 1]`.
