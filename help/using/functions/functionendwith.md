---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: Scopri la funzione endWith
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---


# endWith {#endWith}

Restituisce true se il secondo parametro è un suffisso del primo.

## Categoria

Stringa

## Sintassi delle funzioni

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
