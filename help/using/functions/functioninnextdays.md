---
title: inNextDays
description: Scopri la funzione inNextDays
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
source-wordcount: '44'
ht-degree: 9%

---


# inNextDays {#inNextDays}

Restituisce true se una data o un dateTime specificato è compreso tra ora e ora + giorni delta.

## Categoria

Data

## Sintassi delle funzioni

`inNextDays(<dateTime>,<delta>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora | dateTime |
| delta | integer |

## Firme e tipo restituito

`inNextDays(<dateTime>,<integer>)`

Restituisce un valore booleano.

## Esempi

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Restituisce true.
