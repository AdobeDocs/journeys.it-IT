---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Scopri la funzione notEqualWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 10%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Verificare che la prima stringa argomento con la seconda stringa argomento sia diversa, ignorando le considerazioni relative ai casi.

## Categoria

Stringa

## Sintassi delle funzioni

`notEqualWithIgnoreCase(<parameters>)`

## Parametri

* string

## Firma e tipo restituito

`notEqualWithIgnoreCase(<string>,<string>)`

Restituisce un valore booleano.

## Esempio

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
