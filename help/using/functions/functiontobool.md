---
product: adobe campaign
solution: Journey Orchestration
title: toBool
description: Scopri la funzione toBool
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%

---


# toBool {#toBool}

Converte un valore di argomento in un valore booleano, a seconda del tipo.

* Da stringa: provare a convertire il valore della stringa come valore booleano, da &quot;true&quot; se il valore della stringa è &quot;true&quot;, da &quot;false&quot; in caso contrario
* Da numerico: true se il valore numerico non è uguale a 0, false in caso contrario

## Categoria

Conversione

## Sintassi delle funzioni

`toBool(<parameter>)`

## Parametri

* decimal
* boolean
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
