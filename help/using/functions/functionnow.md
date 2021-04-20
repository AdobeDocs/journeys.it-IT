---
product: adobe campaign
solution: Journey Orchestration
title: now
description: Informazioni sulla funzione
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 11%

---


# now {#now}

Restituisce la data corrente in formato ora data. Per ulteriori informazioni sui tipi di dati, consulta [questa pagina](../expression/data-types.md).

## Categoria

Data

## Sintassi della funzione

`now(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| string |  |

## Firme e tipo restituito

`now()`

`now("<timeZone id>")`

Restituisce un valore dateTime.

## Esempi

`now()`

Restituisce 2019-06-03T06:30Z.

`toString(now())`

Restituisce &quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

Restituisce 2019-06-03T08:30+02:00.