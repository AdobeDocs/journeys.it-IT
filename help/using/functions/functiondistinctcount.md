---
product: adobe campaign
title: distinctCount
description: Scopri la funzione distinctCount
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 32%

---

# distinctCount{#distinctCount}

Conta il numero di valori diversi ignorando i valori nulli.

## Categoria

Aggregazione

## Sintassi della funzione

`distinctCount(<listAny>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| Elenco | listString |
| Elenco | listBoolean |
| Elenco | listInteger |
| Elenco | listDecimal |
| Elenco | listDuration |
| Elenco | listDateTime |
| Elenco | listDateTimeOnly |
| Elenco | listDateOnly |

## Firma e tipo restituito

`distinctCount(<listAny>)`

Restituisce un numero intero.

## Esempio

`distinctCount([10,2,10,null])`

Restituisce 2.
