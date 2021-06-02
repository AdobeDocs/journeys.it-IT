---
product: adobe campaign
title: distinctCountWithNull
description: Scopri la funzione distinctCountWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 27%

---

# distinctCountWithNull {#distinctCountWithNull}

Conta il numero di valori diversi, inclusi i valori nulli.

## Categoria

Aggregazione

## Sintassi della funzione

`distinctCountWithNull(<listAny>)`

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

`distinctCountwithNull(<listAny>)`

Restituisce un numero intero.

## Esempio

`distinctCountWithNull([10,2,10,null])`

Restituisce 3.
