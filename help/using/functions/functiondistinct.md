---
product: adobe campaign
solution: Journey Orchestration
title: distinct
description: Informazioni sulla funzione distinta
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 13%

---


# distinct {#distinct}

Restituisce i valori distinti dell&#39;elenco senza valori null.

## Categoria

Elenco

## Sintassi delle funzioni

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

## Firme e tipi restituiti

`distinct(<listInteger>)`

Restituisce un elenco di interi.

`distinct(<listDecimal>)`

Restituisce un elenco di decimali.

`distinct(<listString>)`

Restituisce un elenco di stringhe.

`distinct(<listDateTimeOnly>)`

Restituisce un elenco di dateTime senza considerare il fuso orario.

`distinct(<listDateTime>)`

Restituisce un elenco di dateTime.

`distinct(<listBoolean>)`

Restituisce un elenco di booleani.

`distinct(<listDuration>)`

Restituisce un elenco delle durate.

## Esempi

`distinct([10,2,10,null])`

Restituisce `[10, 2]`.
