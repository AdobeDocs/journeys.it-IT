---
product: adobe campaign
title: split
description: Scopri la suddivisione della funzione
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 19%

---

# dividere {#split}

Divide la prima stringa argomento con una stringa separatore (seconda stringa argomento, che può essere un’espressione regolare) per generare un elenco di stringhe (token).

## Categoria

Stringa

## Sintassi della funzione

`split(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| stringa di input | stringa |
| stringa separatore | stringa |

## Firme e tipo restituito

`split(<input string>, <separator string>)`

Restituisce un valore listString.

## Esempio

`split(["A_B_C"], "_")`

Restituisce `["A","B","C"]`

Esempio con un campo evento &#39;event.appVersion&#39; con valore: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Restituisce `["20", "45", "2", "3434"]`
