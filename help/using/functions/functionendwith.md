---
product: adobe campaign
title: endWith
description: Scopri la funzione endWith
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

---

# endWith {#endWith}

Restituisce true se il secondo parametro è un suffisso del primo.

## Categoria

Stringa

## Sintassi della funzione

`endWith(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| string | string |
| suffisso | string |

## Firma e tipo restituito

`endWith(<string>,<string>)`

Restituisce un valore booleano.

## Esempio

`endWith("Hello World", "World")`

Restituisce true.

`endWith("Hello World", "Hello")`

Restituisce false.
