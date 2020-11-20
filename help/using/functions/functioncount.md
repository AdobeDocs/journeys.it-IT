---
product: adobe campaign
solution: Journey Orchestration
title: count
description: Ulteriori informazioni sul conteggio delle funzioni
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 22%

---


# count {#count}

Conta gli elementi dell&#39;elenco che non tengono conto dei valori null.

## Categoria

Aggregazione

## Sintassi delle funzioni

`count(<listAny>)`

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

## Firme e tipo restituito

`count(<listAny>)`

Restituisce un numero intero.

## Esempio

`count([10,2,10,null])`

Restituisce 3.
