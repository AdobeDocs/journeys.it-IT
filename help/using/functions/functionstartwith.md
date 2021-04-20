---
product: adobe campaign
solution: Journey Orchestration
title: startWith
description: Scopri la funzione startWith
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 10%

---


# startWith {#startWith}

Restituisce true se il secondo parametro è un prefisso del primo.

## Categoria

Stringa

## Sintassi della funzione

`startWith(<parameters>)`

## Parametri

| Parametro | Tipo |
|-------------|--------|
| string | string |
| prefisso | string |

## Firma e tipo restituito

`startWith(<string>,<string>)`

Restituisce un valore booleano.

## Esempio

`startWith("Hello World", "Hello")`

Restituisce true.

`startWith("Hello World", "World")`

Restituisce false.
