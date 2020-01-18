---
title: distinto
description: Informazioni sulla funzione distinta
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# distinto {#distinct}

Restituisce i valori distinti dell&#39;elenco senza valori null.

## Categoria

Elenco

## Sintassi funzione

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

Restituisce un elenco delle date senza considerare il fuso orario.

`distinct(<listDateTime>)`

Restituisce un elenco di dateTime.

`distinct(<listBoolean>)`

Restituisce un elenco di booleani.

`distinct(<listDuration>)`

Restituisce un elenco delle durate.

## Esempi

`distinct([10,2,10,null])`

Restituisce `[10, 2]`.
