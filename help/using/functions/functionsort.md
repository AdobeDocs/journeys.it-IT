---
product: adobe campaign
title: ordina
description: Scopri l’ordinamento delle funzioni
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 8%

---

# ordina {#sort}

Ordina un elenco di valori o oggetti nell&#39;ordine naturale.

## Categoria

Elenco

## Sintassi della funzione

`sort(<parameters>)`

## Elemento “parameters”

| Parametro | Tipo | Descrizione |
|-----------|------------------|------------------|
| listToSort | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly o listObject | Elenco da ordinare. Per listObject, deve essere un riferimento di campo. |
| keyAttributeName | stringa | Questo parametro è solo per listObject. Il nome dell’attributo negli oggetti dell’elenco specificato viene utilizzato come chiave per l’ordinamento. |
| ordinamentoOrdine | booleano | Crescente (true) o Decrescente (false) |

## Firma e tipo restituito

`sort(<listInteger>,<boolean>)`

Restituisce un elenco di numeri interi.

`sort(<listDecimal>,<boolean>)`

Restituisce un elenco di decimali.

`sort(<listString>,<boolean>)`

Restituisce un elenco di stringhe.

`sort(<listDateTimeOnly>,<boolean>)`

Restituisce un elenco di date senza considerare il fuso orario.

`sort(<listDateTime>,<boolean>)`

Restituisce un elenco di date.

`sort(<listDateOnly>,<boolean>)`

Restituisce un elenco di date.

`sort(<listBoolean>,<boolean>)`

Restituisce un elenco di booleani.

`sort(<listObject>,<string>,<boolean>)`

Restituisce un elenco di oggetti.

## Esempio

`sort(["A", "C", "B"], true)`

Restituisce `["A","B","C"]`.

`sort([1, 3, 2], false)`

Restituisce `[3, 2, 1]`.

