---
product: adobe campaign
solution: Journey Orchestration
title: substr
description: Scopri il substr funzione
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 6%

---


# substr {#substr}

Restituisce la sottostringa dell&#39;espressione stringa tra l&#39;indice start e l&#39;indice end. Se l&#39;indice finale non è definito, si trova tra l&#39;indice iniziale e la fine.

## Categoria

Stringa

## Sintassi delle funzioni

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