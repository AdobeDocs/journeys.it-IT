---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: Informazioni sulla funzione countOnlyNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 23%

---


# countOnlyNull {#countOnlyNull}

Conta il numero di valori null nell&#39;elenco.

## Categoria

Aggregazione

## Sintassi delle funzioni

`countOnlyNull(<listAny>)`

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

## Firma e tipo restituito

`countOnlyNull(<listAny>)`

Restituisce un numero intero.

## Esempio

`count([10,2,10,null])`

Restituisce 1.
