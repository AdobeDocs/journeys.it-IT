---
product: adobe campaign
solution: Journey Orchestration
title: now
description: Scopri la funzione
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 10%

---


# now {#now}

Restituisce la data corrente in formato ora data. Per ulteriori informazioni sui tipi di dati, fare riferimento a [questa pagina](../expression/data-types.md).

## Categoria

Data

## Sintassi delle funzioni

`now(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| string |  |

## Firme e tipo restituito

`now()`

`now("<timeZone id>")`

Restituisce un dateTime.

## Esempi

`now()`

Restituisce 2019-06-03T06:30Z.

`toString(now())`

Restituisce &quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

Restituisce 2019-06-03T08:30+02:00.