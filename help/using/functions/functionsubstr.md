---
title: substr
description: Scopri il substr funzione
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# substr {#substr}

Restituisce la sottostringa dell&#39;espressione stringa tra l&#39;indice start e l&#39;indice end. Se l&#39;indice finale non è definito, si trova tra l&#39;indice iniziale e la fine.

## Categoria

Stringa

## Sintassi funzione

`substr(<parameters>)`

## Parametri

| Parametro | type |
|-------------|----------|
| string | string |
| beginIndex | integer |
| endIndex | integer |

## Firma e tipo restituito

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Restituisce una stringa.

## Esempio

`substr("Hello World",6)`

Restituisce &quot;World&quot;.

`substr("Hello World", 0, 5)`

Restituisce &quot;Hello&quot;.