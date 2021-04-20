---
product: adobe campaign
solution: Journey Orchestration
title: toBool
description: Scopri la funzione toBool
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 6%

---


# toBool {#toBool}

Converte un valore di argomento in un valore booleano, a seconda del tipo.

* Stringa da: prova a convertire il valore della stringa come booleano, da &quot;true&quot; se il valore della stringa è &quot;true&quot;, false in caso contrario
* Da dati numerici: true se il valore numerico non è uguale a 0, false in caso contrario

## Categoria

Conversione

## Sintassi della funzione

`toBool(<parameter>)`

## Parametri

* decimale
* booleano
* string
* integer

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
