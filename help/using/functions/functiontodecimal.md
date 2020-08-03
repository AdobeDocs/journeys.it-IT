---
title: toDecimal
description: Scopri la funzione toDecimal
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 5%

---


# toDecimal {#toDecimal}

Converte un valore argomento in un valore decimale, a seconda del tipo.

## Categoria

Conversione

## Sintassi delle funzioni

`toDecimal(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| string | converte il valore della stringa come valore decimale |
| dateTime | converte la data come numero di millisecondi (epoch millisecondi) |
| boolean | converte il valore booleano in 1 se true, 0 se false |
| integer | converte in decimale (ad esempio.: 1 diventa 1,0) |

## Firme e tipi restituiti

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Restituisce un decimale.

## Esempi

`toDecimal("4.0")`

Restituisce 4,0.
