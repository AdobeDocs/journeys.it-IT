---
product: adobe campaign
solution: Journey Orchestration
title: random
description: Scopri la funzione a caso
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%

---


# random {#random}

Genera un numero casuale compreso tra 0 e 1.

## Categoria

Percorsi

## Sintassi delle funzioni

`random(<parameters>)`

## Firma e tipo restituito

`random()`

Restituisce un valore decimale.

## Esempio

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Spiegazione: se il rapporto di successo non ha alcun valore/è nullo, il valore predefinito sarà applicato e sarà una figura casuale compresa tra 0 e 1 * 100 (ovvero da 0 a 100).
