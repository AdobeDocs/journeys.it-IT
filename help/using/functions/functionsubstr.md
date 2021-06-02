---
product: adobe campaign
title: substr
description: Informazioni sul substr funzione
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 9%

---

# substr {#substr}

Restituisce la sottostringa dell&#39;espressione stringa tra l&#39;indice begin e l&#39;indice end. Se l&#39;indice finale non è definito, si trova tra l&#39;indice iniziale e la fine.

## Categoria

Stringa

## Sintassi della funzione

`substr(<parameters>)`

## Elemento “parameters”

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
