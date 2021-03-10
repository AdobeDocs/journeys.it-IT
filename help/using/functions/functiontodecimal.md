---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: Scopri la funzione suDecimal
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 8%

---


# toDecimal {#toDecimal}

Converte un valore di argomento in un valore decimale, a seconda del tipo.

## Categoria

Conversione

## Sintassi della funzione

`toDecimal(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| string | converte il valore della stringa come decimale |
| dateTime | converte la data come numero di millisecondi (epoch millisecondi) |
| booleano | converte il valore booleano in 1 se true, 0 se false |
| integer | converte in un decimale (ad esempio.: 1 diventa 1,0) |

## Firme e tipi restituiti

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Restituisce un decimale.

## Esempi

`toDecimal("4.0")`

Restituisce 4,0.
