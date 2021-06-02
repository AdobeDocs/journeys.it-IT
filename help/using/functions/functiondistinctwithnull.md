---
product: adobe campaign
title: distinctWithNull
description: Scopri la funzione distinctWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 13%

---

# distinctWithNull {#distinctWithNull}

Restituisce i valori distinti dell’elenco. Se l’elenco contiene almeno un valore nullo, nell’elenco restituito sarà presente un valore nullo.

## Categoria

Elenco

## Sintassi della funzione

`distinctWithNull(<parameter>)`

## Elemento “parameters”

| Parametro | Tipo |
|-----------|------------------|
| Elenco | listString |
| Elenco | listBoolean |
| Elenco | listInteger |
| Elenco | listDecimal |
| Elenco | listDuration |
| Elenco | listDateTime |
| Elenco | listDateTimeOnly |

## Firme e tipi restituiti

`distinctWithNull(<listInteger>)`

Restituisce un elenco di numeri interi.

`distinctWithNull(<listDecimal>)`

Restituisce un elenco di decimali.

`distinctWithNull(<listString>)`

Restituisce un elenco di stringhe.

`distinctWithNull(<listDateTimeOnly>)`

Restituisce un elenco di date senza considerare il fuso orario.

`distinctWithNull(<listDateTime>)`

Restituisce un elenco di date.

`distinctWithNull(<listBoolean>)`

Restituisce un elenco di booleani.

`distinctWithNull(<listDuration>)`

Restituisce un elenco di durate.

## Esempi

`distinctWithNull([10,2,10,null])`

Restituisce [10, 2, null]
