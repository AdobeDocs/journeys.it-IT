---
product: adobe campaign
solution: Journey Orchestration
title: endWithIgnoreCase
description: Scopri la funzione endWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 5%

---


# endWithIgnoreCase {#endWithIgnoreCase}

Controlla se la prima stringa di argomento termina con una stringa specifica (seconda stringa di argomento), senza tenere conto del caso.

## Categoria

Stringa

## Sintassi della funzione

`endWithIgnoreCase(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| string | string |
| suffisso | string |

## Firma e tipo restituito

`endWithIgnoreCase(<string>,<string>)`

Restituisce un valore booleano.

## Esempio

`endWithIgnoreCase("rowing is great', "AT")`

Restituisce true.
