---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: Informazioni sulla funzione toInteger
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 7%

---


# toInteger {#toInteger}

Converte un valore argomento in un numero intero.

## Categoria

Conversione

## Sintassi delle funzioni

`toInteger(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| string | converte il valore della stringa come numero intero |
| dateTime | converte la data come numero di millisecondi (epoch millisecondi) |
| decimal | converte in numero intero rimuovendo la parte decimale (ad esempio: 1,5 diventa 1) |
| boolean | converte il valore booleano in 1 se true, 0 se false |

## Firme e tipo restituito

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Restituisce un numero intero.

## Esempi

`toInteger(4)`

Restituisce 4.
