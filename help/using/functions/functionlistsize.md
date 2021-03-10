---
product: adobe campaign
solution: Journey Orchestration
title: listSize
description: Scopri la funzione listSize
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 24%

---


# listSize {#listSize}

Conta il numero di elementi nell’elenco.

## Categoria

Elenco

## Sintassi della funzione

`listSize(<parameters>)`

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

## Firme e tipo restituito

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

Restituisce un numero intero.

## Esempio

`listSize([10,2,3])`

Restituisce 3.
