---
title: now
description: Scopri la funzione
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 10%

---


# now {#now}

Restituisce la data corrente in formato ora data. Per ulteriori informazioni sui tipi di dati, fare riferimento a [](../expression/data-types.md).

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