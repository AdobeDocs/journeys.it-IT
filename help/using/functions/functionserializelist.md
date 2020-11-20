---
product: adobe campaign
solution: Journey Orchestration
title: serializeList
description: Scopri la funzione serializeList
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 15%

---


# serializeList {#serializeList}

Converte in una stringa l&#39;elenco (qualsiasi tipo) fornito nel primo parametro. Il secondo parametro rappresenta il separatore da utilizzare. Il terzo parametro è un valore booleano che indica se ogni elemento dell&#39;espressione deve includere virgolette.

## Categoria

Elenco

## Sintassi delle funzioni

`serializeList(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| Stringa | Stringa |
| Booleano | Booleano |
| DateTimeOnly | DateTimeOnly |
| Elenco | listString |
| Elenco | listBoolean |
| Elenco | listPoint |
| Elenco | listDecimal |
| Elenco | listDuration |
| Elenco | listDateTime |
| Elenco | listDateTimeOnly |

## Firma e tipo restituito

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Restituisce una stringa.

## Esempio

`serializeList(["Hello","World"], " ", false)`

Restituisce &quot;Hello World&quot;.

`serializeList(["Hello", "World"], ",", true)`

Restituisce &quot;&quot;Hello&quot;,&quot;World&quot;.
