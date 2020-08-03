---
title: inNextYear
description: Scopri la funzione inNextYears
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1441402b50414443a6b6bb3087cf648cc74faa49
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextYear {#inNextYears}

Restituisce true se una data o un dateTime specificato è compreso tra ora e ora + anni delta.

## Categoria

Data

## Sintassi delle funzioni

`inNextYears(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora | dateTime |
| delta | integer |

## Firme e tipo restituito

`inNextYears(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

Restituisce true.
