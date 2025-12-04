---
product: adobe campaign
title: concatena
description: Informazioni sulla concatenazione delle funzioni
feature: Journeys
role: Developer
level: Experienced
exl-id: 7a516705-2bbe-4b42-97fc-aeae11082002
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 27%

---

# concatena {#concat}

Concatena due parametri di stringa o un elenco di stringhe.

## Categoria

Stringa

## Sintassi della funzione

`concat(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| Elenco | listString |
| stringa | stringa |

## Firma e tipo restituito

`concat(<string>,<string>)`

`concat(<listString>)`

Restituisce una stringa.

## Esempio

`concat("Hello","World")`

Restituisce &quot;HelloWorld&quot;.

`concat(["Hello"," ","World"])`

Restituisce &quot;Hello World&quot;.
