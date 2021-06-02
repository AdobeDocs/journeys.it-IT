---
product: adobe campaign
title: distinctCount
description: Scopri la funzione distinctCount
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 27%

---

# distinctCount{#distinctCount}

Conta il numero di valori diversi ignorando i valori nulli.

## Categoria

Aggregazione

## Sintassi della funzione

`distinctCount(<listAny>)`

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

## Firma e tipo restituito

`distinctCount(<listAny>)`

Restituisce un numero intero.

## Esempio

`distinctCount([10,2,10,null])`

Restituisce 2.
