---
product: adobe campaign
solution: Journey Orchestration
title: startWith
description: Informazioni sulla funzione startWith
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---


# startWith {#startWith}

Restituisce true se il secondo parametro è un prefisso del primo.

## Categoria

Stringa

## Sintassi delle funzioni

`startWith(<parameters>)`

## Parametri

| Parametro | Tipo |
|-------------|--------|
| string | string |
| prefix | string |

## Firma e tipo restituito

`startWith(<string>,<string>)`

Restituisce un valore booleano.

## Esempio

`startWith("Hello World", "Hello")`

Restituisce true.

`startWith("Hello World", "World")`

Restituisce false.
