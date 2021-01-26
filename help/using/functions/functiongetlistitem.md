---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: Scopri la funzione gstListItem
translation-type: tm+mt
source-git-commit: 5539ea0e8f124896f5599dba63babaa3e5b0229b
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 3%

---


# getListItem {#gestListItem}

Restituisce l&#39;elemento dell&#39;elenco in corrispondenza dell&#39;indice specificato.

## Categoria

Elenco

## Sintassi delle funzioni

`getListItem(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| index | integer |

## Firme e tipo restituito

`getListItem(<listInteger>,<index>)`

Restituisce un elenco di interi.

`getListItem(<listDecimal>,<index>)`

Restituisce un elenco di decimali.

`getListItem(<listString>,<index>)`

Restituisce un elenco di stringhe.

`getListItem(<listDateTimeOnly>,<index>)`

Restituisce un elenco di dateTime senza considerare il fuso orario.

`getListItem(<listDateTime>,<index>)`

Restituisce un elenco di dateTime.

`getListItem(<listBoolean>,<index>)`

Restituisce un elenco di booleani.

`getListItem(<listDuration>,<index>)`

Restituisce un elenco delle durate.

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