---
product: adobe campaign
solution: Journey Orchestration
title: random
description: Scopri la funzione casuale
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 5%

---


# random {#random}

Genera un numero casuale compreso tra 0 e 1.

## Categoria

Percorsi

## Sintassi della funzione

`random(<parameters>)`

## Firma e tipo restituito

`random()`

Restituisce un decimale.

## Esempio

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Spiegazione: se il rapporto di successo non ha valore/è nullo, viene applicato il valore predefinito e sarà una figura casuale compresa tra 0 e 1 * 100 (ovvero da 0 a 100).
