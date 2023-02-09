---
product: adobe campaign
title: limit
description: Scopri il limite di funzioni
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e006660-1206-4b8a-9e5b-c6fbeee9cc8f
source-git-commit: 9f5ef0497227a370e2e1f4a62450611ae2e336b9
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 9%

---

# limit {#limit}

Restituisce il primo o l’ultimo N elementi di un elenco.

## Categoria

Elenco

## Sintassi della funzione

`limit(<parameters>)`

## Parametri

| Parametro | Tipo | Descrizione |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly o listObject | Elenco da ordinare. Per listObject, deve essere un riferimento di campo. |
| numberOfItems | numero intero | Numero di elementi da restituire dall’elenco specificato. |
| firstOrLastItems | booleano | Questo parametro è facoltativo (true per impostazione predefinita). true restituisce i primi elementi. false restituisce gli ultimi elementi. |

## Firma e tipo restituito

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

Restituisce un elenco di stringhe.

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

Restituisce un elenco di numeri interi.

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

Restituisce un elenco di decimali.

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

Restituisce un elenco di booleani.

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

Restituisce un elenco di date.

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Restituisce un elenco di date senza considerare il fuso orario.

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

Restituisce un elenco di date.

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

Restituisce un elenco di durate.

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

Restituisce un elenco di oggetti.

## Esempio

`limit(["A", "B", "C", "D", "E"], 3)`

Restituisce `["A","B","C"]`.

`limit(["A", "B", "C", "D", "E"], 3, false)`

Restituisce `["C","D","E"]`.
