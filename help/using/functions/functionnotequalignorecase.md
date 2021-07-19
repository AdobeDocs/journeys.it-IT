---
product: adobe campaign
title: notEqualWithIgnoreCase
description: Scopri la funzione notEqualWithIgnoreCase
feature: Percorsi
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 18%

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
