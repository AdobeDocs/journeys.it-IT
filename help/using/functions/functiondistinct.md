---
product: adobe campaign
title: distinct
description: Scopri il distinto funzione
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 18%

---

# distinto {#distinct}

Restituisce i valori distinti dell’elenco senza valori nulli.

## Categoria

Elenco

## Sintassi della funzione

`distinct(<parameter>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| Elenco | listString |
| Elenco | listBoolean |
| Elenco | listInteger |
| Elenco | listDecimal |
| Elenco | listDuration |
| Elenco | listDateTime |
| Elenco | listDateTimeOnly |
| Elenco | listDateOnly |

## Firme e tipi restituiti

`distinct(<listInteger>)`

Restituisce un elenco di numeri interi.

`distinct(<listDecimal>)`

Restituisce un elenco di decimali.

`distinct(<listString>)`

Restituisce un elenco di stringhe.

`distinct(<listDateTimeOnly>)`

Restituisce un elenco di date senza considerare il fuso orario.

`distinct(<listDateTime>)`

Restituisce un elenco di date.

`distinct(<listDateOnly>)`

Restituisce un elenco di date.

`distinct(<listBoolean>)`

Restituisce un elenco di booleani.

`distinct(<listDuration>)`

Restituisce un elenco di durate.

## Esempi

`distinct([10,2,10,null])`

Restituisce `[10, 2]`.
