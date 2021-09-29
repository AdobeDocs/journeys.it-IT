---
product: adobe campaign
title: toDateOnly
description: Scopri la funzione toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5e2af021f1c82063fcc0d4e4b5edf13c57cc6c72
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 17%

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
| data in formato ISO-8601 o &quot;AAAA-MM-GG&quot; (formato XDM Data) | stringa |
| data | data |

## Firme e tipi restituiti

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Restituisce un datetime senza considerare il fuso orario.

## Esempi

`toDateOnly("2016-08-18")`

restituisce un oggetto dateOnly che rappresenta 2016-08-18.