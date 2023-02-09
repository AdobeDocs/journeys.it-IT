---
product: adobe campaign
title: toDateOnly
description: Scopri la funzione toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 21%

---

# toDateOnly{#toDateOnly}

Converte un valore di argomento in un valore di sola data.

## Categoria

Conversione

## Sintassi della funzione

`toDateOnly(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data in formato ISO-8601 o &quot;AAAA-MM-GG&quot; (formato XDM Data) | string |
| data | data |

## Firme e tipi restituiti

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Restituisce un datetime senza considerare il fuso orario.

## Esempi

`toDateOnly("2016-08-18")`

restituisce un oggetto dateOnly che rappresenta 2016-08-18.
