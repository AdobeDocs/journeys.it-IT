---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Scopri la funzione notEqualWithIgnoreCase
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 12%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Verificare che la prima stringa di argomento con la seconda stringa di argomento sia diversa, ignorando le considerazioni relative a maiuscole e minuscole.

## Categoria

Stringa

## Sintassi della funzione

`notEqualWithIgnoreCase(<parameters>)`

## Parametri

* string

## Firma e tipo restituito

`notEqualWithIgnoreCase(<string>,<string>)`

Restituisce un valore booleano.

## Esempio

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
