---
product: adobe campaign
title: endWithIgnoreCase
description: Scopri la funzione endWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 8%

---

# endWithIgnoreCase {#endWithIgnoreCase}

Controlla se la prima stringa di argomento termina con una stringa specifica (seconda stringa di argomento), senza tenere conto del caso.

## Categoria

Stringa

## Sintassi della funzione

`endWithIgnoreCase(<parameters>)`

## Elemento “parameters”

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
