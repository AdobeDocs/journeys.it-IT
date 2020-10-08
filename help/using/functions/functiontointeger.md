---
title: toInteger
description: Informazioni sulla funzione toInteger
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
