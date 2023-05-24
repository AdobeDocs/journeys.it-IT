---
product: adobe campaign
title: distinctWithNull
description: Scopri la funzione distinctWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 5%

---

# distinctWithNull {#distinctWithNull}

Restituisce i valori o gli oggetti distinti di un elenco specifico. Se l&#39;elenco include almeno una voce Null, nell&#39;elenco restituito sarà presente una voce Null.

## Categoria

Elenco

## Sintassi della funzione

`distinctWithNull(<parameters>)`

## Parametri

| Parametro | Tipo | Descrizione |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly o listObject | Elenco da elaborare. Per listObject, deve essere un riferimento di campo. |
| keyAttributeName | string | Questo parametro è facoltativo e solo per listObject. Se il parametro non viene fornito, un oggetto viene considerato duplicato se tutti gli attributi hanno gli stessi valori. In caso contrario, un oggetto viene considerato duplicato se l’attributo specificato ha lo stesso valore. |

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

`distinctWithNull(<listDateOnly>)`

Restituisce un elenco di date.

`distinctWithNull(<listBoolean>)`

Restituisce un elenco di booleani.

`distinctWithNull(<listDuration>)`

Restituisce un elenco di durate.

`distinctWithNull(<listObject>)`

`distinctWithNull(<listObject>,<string>)`

Restituisce un elenco di oggetti.

## Esempi

`distinctWithNull([10,2,10,null])`

Restituisce [10, 2, null]
