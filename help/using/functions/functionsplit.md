---
product: adobe campaign
solution: Journey Orchestration
title: split
description: Scopri la divisione della funzione
translation-type: tm+mt
source-git-commit: 135485c097f99483c2ddb3d03e0552f9ac134b44
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 4%

---


# split {#split}

Divide la prima stringa argomento con una stringa separatore (seconda stringa argomento, che può essere un&#39;espressione regolare) per generare un elenco di stringhe (token).

## Categoria

Stringa

## Sintassi delle funzioni

`split(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| stringa di input | string |
| stringa separatore | string |

## Firme e tipo restituito

`split(<input string>, <separator string>)`

Restituisce un valore listString.

## Esempio

`split(["A_B_C"], "_")`

Restituisce `["A","B","C"]`

Esempio con un campo evento &#39;event.appVersion&#39; con valore: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Restituisce `["20", "45", "2", "3434"]`
