---
product: adobe campaign
title: countWithNull
description: Scopri la funzione countWithNull
feature: Journeys
role: Developer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%
---
# countWithNull {#countWithNull}

Conta tutti gli elementi dell’elenco, inclusi i valori Null.

## Categoria

Aggregazione

## Sintassi della funzione

`countWithNull(<listAny>)`

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
| Elenco | listDateOnly |

## Firma e tipo restituito

`countWithNull(<listAny>)`

Restituisce un numero intero.

## Esempio

`countWithNull([10,2,10,null])`

Restituisce 4.
