---
product: adobe campaign
title: random
description: Scopri la funzione casuale
feature: Percorsi
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 11%

---

# casuale {#random}

Genera un numero casuale compreso tra 0 e 1.

## Categoria

Operazioni matematiche

## Sintassi della funzione

`random(<parameters>)`

## Firma e tipo restituito

`random()`

Restituisce un decimale.

## Esempio

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Spiegazione: se il rapporto di successo non ha valore/è nullo, viene applicato il valore predefinito e sarà una figura casuale compresa tra 0 e 1 * 100 (ovvero da 0 a 100).
