---
title: distinctWithNull
description: Scopri la funzione separateWithNull
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
