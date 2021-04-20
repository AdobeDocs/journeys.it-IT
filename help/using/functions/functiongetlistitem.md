---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: Scopri la funzione gstListItem
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 4%

---


# getListItem {#gestListItem}

Restituisce l&#39;elemento dell&#39;elenco in corrispondenza dell&#39;indice specificato.

## Categoria

Elenco

## Sintassi della funzione

`getListItem(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| elenco | listString |
| elenco | listBoolean |
| elenco | listInteger |
| elenco | listDecimal |
| elenco | listDuration |
| elenco | listDateTime |
| elenco | listDateTimeOnly |
| index | integer |

## Firme e tipo restituito

`getListItem(<listInteger>,<index>)`

Restituisce un elenco di numeri interi.

`getListItem(<listDecimal>,<index>)`

Restituisce un elenco di decimali.

`getListItem(<listString>,<index>)`

Restituisce un elenco di stringhe.

`getListItem(<listDateTimeOnly>,<index>)`

Restituisce un elenco di date senza considerare il fuso orario.

`getListItem(<listDateTime>,<index>)`

Restituisce un elenco di date.

`getListItem(<listBoolean>,<index>)`

Restituisce un elenco di booleani.

`getListItem(<listDuration>,<index>)`

Restituisce un elenco di durate.

## Esempio

`getListItem([10, 2, 3], 1)`

Restituisce &quot;2&quot;

`getListItem(["A", "B", "C"], 3)`
Restituisce &quot;C&quot;

Esempi con un campo evento &#39;event.appVersion&#39; con valore: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Restituisce `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Restituisce &quot;20&quot;