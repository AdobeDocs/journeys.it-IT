---
title: serializeList
description: Scopri la funzione serializeList
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# serializeList {#serializeList}

Converte in una stringa l&#39;elenco (qualsiasi tipo) fornito nel primo parametro. Il secondo parametro rappresenta il separatore da utilizzare. Il terzo parametro è un valore booleano che indica se ogni elemento dell&#39;espressione deve includere virgolette.

## Categoria

Elenco

## Sintassi funzione

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
