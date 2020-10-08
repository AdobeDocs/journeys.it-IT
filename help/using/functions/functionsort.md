---
title: sort
description: Informazioni sull'ordinamento delle funzioni
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
source-wordcount: '104'
ht-degree: 10%

---


# sort {#sort}

Ordina un elenco di valori nell&#39;ordine naturale. Il primo argomento è l&#39;elenco di valori, il secondo è un valore booleano che indica se l&#39;ordinamento è crescente (true) o decrescente (false).

## Categoria

Elenco

## Sintassi delle funzioni

`sort(<parameters>)`

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
| Booleano | Booleano |

## Firma e tipo restituito

`sort(<listInteger>,<boolean>)`

Restituisce un elenco di interi.

`sort(<listDecimal>,<boolean>)`

Restituisce un elenco di decimali.

`sort(<listString>,<boolean>)`

Restituisce un elenco di stringhe.

`sort(<listDateTimeOnly>,<boolean>)`

Restituisce un elenco di dateTime senza considerare il fuso orario.

`sort(<listDateTime>,<boolean>)`

Restituisce un elenco di dateTime.

`sort(<listBoolean>,<boolean>)`

Restituisce un elenco di booleani.

## Esempio

`sort(["A", "C", "B"], true)`

Restituisce `["A","B","C"]`.

`sort([1, 3, 2], false)`

Restituisce `[3, 2, 1]`.
