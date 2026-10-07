---
product: adobe campaign
title: toBool
description: Scopri la funzione toBool
feature: Journeys
role: Developer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
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
source-wordcount: '75'
ht-degree: 12%
---
# toBool {#toBool}

Converte un valore di argomento in un valore booleano, a seconda del tipo.

* Da stringa: prova a convertire il valore stringa come booleano; da &quot;true&quot; se il valore stringa è &quot;true&quot;; in caso contrario false
* Dal valore numerico: true se il valore numerico non è uguale a 0, false in caso contrario

## Categoria

Conversione

## Sintassi della funzione

`toBool(<parameter>)`

## Parametri

* decimale
* booleano
* stringa
* intero

## Firme e tipi restituiti

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Restituisce un valore booleano.

## Esempi

`toBool("true")`

`toBool(1)`

Restituisce true.

`toBool("this is not a boolean")`

Restituisce false.
