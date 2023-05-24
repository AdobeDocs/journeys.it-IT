---
product: adobe campaign
title: getListItem
description: Scopri la funzione gstListItem
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 21%

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
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| list | listDateOnly |
| index | numero intero |

## Firme e tipo restituito

`getListItem(<listInteger>,<index>)`

Restituisce un numero intero.

`getListItem(<listDecimal>,<index>)`

Restituisce un valore decimale.

`getListItem(<listString>,<index>)`

Restituisce una stringa.

`getListItem(<listDateTimeOnly>,<index>)`

Restituisce un valore datetime senza considerare il fuso orario.

`getListItem(<listDateTime>,<index>)`

Restituisce un valore datetime.

`getListItem(<listDateOnly>,<index>)`

Restituisce un elenco di date.

`getListItem(<listBoolean>,<index>)`

Restituisce un valore booleano.

`getListItem(<listDuration>,<index>)`

Restituisce una durata.

## Esempio

`getListItem([10, 2, 3], 1)`

Restituisce &quot;2&quot;

`getListItem(["A", "B", "C"], 2)`
Restituisce &quot;C&quot;

Esempi con un campo evento &quot;event.appVersion&quot; con valore: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Restituisce `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Restituisce &quot;20&quot;
