---
title: distinct
description: Informazioni sulla funzione distinta
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
