---
product: adobe campaign
title: count
description: Informazioni sul conteggio delle funzioni
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%

---

# count {#count}

Conta gli elementi dell’elenco che non tengono conto dei valori nulli.

## Categoria

Aggregazione

## Sintassi della funzione

`count(<listAny>)`

## Elemento “parameters”

| Parametro | Tipo |
|-----------|------------------|
| Elenco | listString |
| Elenco | listBoolean |
| Elenco | listInteger |
| Elenco | listDecimal |
| Elenco | listDuration |
| Elenco | listDateTime |
| Elenco | listDateTimeOnly |

## Firme e tipo restituito

`count(<listAny>)`

Restituisce un numero intero.

## Esempio

`count([10,2,10,null])`

Restituisce 3.
