---
title: endWith
description: Scopri la funzione endWith
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a844adc1a073aebfb7fd8a719e52f305079260b7
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 6%

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
