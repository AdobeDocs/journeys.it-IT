---
product: adobe campaign
title: toDecimal
description: Learn about the function toDecimal
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 14%

---

# toDecimal {#toDecimal}

Converte un valore di argomento in un valore decimale, a seconda del tipo.

## Categoria

Conversione

## Function syntax

`toDecimal(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| stringa | converte il valore della stringa come decimale |
| dateTime | converte la data come numero di millisecondi (epoch millisecondi) |
| booleano | converts the boolean value as 1 if true, 0 if false |
| integer | converts to a decimal (example.: 1 diventa 1,0) |

## Firme e tipi restituiti

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Restituisce un decimale.

## Esempi

`toDecimal("4.0")`

Returns 4.0.
