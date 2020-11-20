---
product: adobe campaign
solution: Journey Orchestration
title: distinctWithNull
description: Scopri la funzione separateWithNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 11%

---


# distinctWithNull {#distinctWithNull}

Restituisce i valori distinti dell&#39;elenco. Se nell&#39;elenco è presente almeno un valore null, nell&#39;elenco restituito verrà incluso un valore null.

## Categoria

Elenco

## Sintassi delle funzioni

`distinctWithNull(<parameter>)`

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

## Firme e tipi restituiti

`distinctWithNull(<listInteger>)`

Restituisce un elenco di interi.

`distinctWithNull(<listDecimal>)`

Restituisce un elenco di decimali.

`distinctWithNull(<listString>)`

Restituisce un elenco di stringhe.

`distinctWithNull(<listDateTimeOnly>)`

Restituisce un elenco di dateTime senza considerare il fuso orario.

`distinctWithNull(<listDateTime>)`

Restituisce un elenco di dateTime.

`distinctWithNull(<listBoolean>)`

Restituisce un elenco di booleani.

`distinctWithNull(<listDuration>)`

Restituisce un elenco delle durate.

## Esempi

`distinctWithNull([10,2,10,null])`

Restituisce [10, 2, null]
