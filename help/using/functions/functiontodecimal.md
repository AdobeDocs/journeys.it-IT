---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: Scopri la funzione toDecimal
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 7%

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
