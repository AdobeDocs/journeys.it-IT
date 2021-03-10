---
product: adobe campaign
solution: Journey Orchestration
title: split
description: Scopri la suddivisione della funzione
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 7%

---


# split {#split}

Divide la prima stringa argomento con una stringa separatore (seconda stringa argomento, che può essere un’espressione regolare) per generare un elenco di stringhe (token).

## Categoria

Stringa

## Sintassi della funzione

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
