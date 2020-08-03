---
title: random
description: Scopri la funzione a caso
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 3%

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
