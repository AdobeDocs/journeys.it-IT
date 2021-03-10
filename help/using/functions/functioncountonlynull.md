---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: Scopri la funzione countOnlyNull
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 24%

---


# countOnlyNull {#countOnlyNull}

Conta il numero di valori nulli nell’elenco.

## Categoria

Aggregazione

## Sintassi della funzione

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

Restituisce un numero intero.

## Esempio

`count([10,2,10,null])`

Restituisce 1.
