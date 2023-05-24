---
product: adobe campaign
title: toInteger
description: Scopri la funzione toInteger
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 15%

---

# toInteger {#toInteger}

Converte un valore di argomento in un numero intero.

## Categoria

Conversione

## Sintassi della funzione

`toInteger(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| string | converte il valore stringa come numero intero |
| dateTime | converte la data in millisecondi (millisecondi epoca) |
| decimal | converte in numero intero rimuovendo la parte decimale (ad esempio: 1,5 diventa 1) |
| booleano | converte il valore booleano come 1 se true, 0 se false |

## Firme e tipo restituito

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Restituisce un numero intero.

## Esempi

`toInteger("4")`

Restituisce 4.
