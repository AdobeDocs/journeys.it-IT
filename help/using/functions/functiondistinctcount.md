---
product: adobe campaign
solution: Journey Orchestration
title: distinctCount
description: Scopri la funzione distinctCount
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 23%

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

## Firma e tipo restituito

`distinctCount(<listAny>)`

Restituisce un numero intero.

## Esempio

`distinctCount([10,2,10,null])`

Restituisce 2.
