---
product: adobe campaign
title: nowWithDelta
description: Scopri la funzione nowWithDelta
feature: Journeys
role: Developer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
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
source-wordcount: '110'
ht-degree: 7%
---
# nowWithDelta {#nowWithDelta}

Restituisce il valore datetime corrente comprensivo di un offset. Se viene specificato un ID di fuso orario, verrà applicato lo scostamento del fuso orario. Per ulteriori informazioni sui tipi di dati, consultare [questa pagina](../expression/data-types.md).

## Categoria

Data

## Sintassi della funzione

`nowWithDelta(<parameters>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| delta | valore intero positivo o negativo |
| parte data | anni, mesi, giorni, ore, minuti o secondi come stringa |
| id fuso orario | rappresentazione stringa del valore del fuso orario. Per ulteriori informazioni, vedere [Tipi di dati](../expression/data-types.md). L’ID del fuso orario deve essere una costante stringa. Non può essere un riferimento di campo né un&#39;espressione. |

## Firme e tipo restituito

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Restituisce un valore dateTime.

## Esempi

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Restituisce un valore dateTime esattamente 2 ore fa.
