---
product: adobe campaign
title: toDateOnly
description: Scopri la funzione toDateOnly
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 16%

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
| data in formato ISO-8601 o &quot;AAAA-MM-GG&quot; (formato data XDM) | stringa |
| data | data |

## Firme e tipi restituiti

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Restituisce un valore datetime senza considerare il fuso orario.

## Esempi

`toDateOnly("2016-08-18")`

restituisce un oggetto dateOnly che rappresenta il 18/08/2016.
