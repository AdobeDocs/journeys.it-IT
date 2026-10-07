---
product: adobe campaign
title: matchRegExp
description: Scopri la funzione matchRegExp
feature: Journeys
role: Developer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
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
source-wordcount: '61'
ht-degree: 18%
---
# matchRegExp {#matchRegExp}

Restituisce true se la stringa nel primo parametro corrisponde all&#39;espressione regolare nel secondo parametro. Per ulteriori informazioni, vedere [questa pagina](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Categoria

Stringa

## Sintassi della funzione

`matchRegExp(<parameters>)`

## Parametri

| Parametro | Tipo |
|--- |--- |
| stringa | stringa |
| regexp | stringa |

## Firma e tipo restituito

`matchRegExp(<string>,<string>)`

Restituisce un valore booleano.

## Esempio

`matchRegExp("username@adobe.com", "*adobe")`

Restituisce true.
