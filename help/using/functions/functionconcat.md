---
product: adobe campaign
solution: Journey Orchestration
title: concat
description: Scopri la funzione concat
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 13%

---


# concat {#concat}

Concatena due parametri di stringa o un elenco di stringhe.

## Categoria

Stringa

## Sintassi della funzione

`concat(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| Elenco | listString |
| string | string |

## Firma e tipo restituito

`concat(<string>,<string>)`

`concat(<listString>)`

Restituisce una stringa.

## Esempio

`concat("Hello","World")`

Restituisce &quot;HelloWorld&quot;.

`concat(["Hello"," ","World"])`

Restituisce &quot;Hello World&quot;.
