---
product: adobe campaign
title: startWithIgnoreCase
description: Scopri la funzione startWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 25%

---

# startWithIgnoreCase {#startWithIgnoreCase}

Restituisce true se il secondo parametro è un prefisso del primo senza considerare la distinzione tra maiuscole e minuscole.

## Categoria

Stringa

## Sintassi della funzione

`startWithIgnoreCase(<parameters>)`

## Elemento “parameters”

| Parametro | Tipo |
|-------------|--------|
| stringa | stringa |
| prefisso | stringa |

## Firma e tipo restituito

`startWithIgnoreCase(<string>,<string>)`

Restituisce un valore booleano.

## Esempio

`startWithIgnoreCase("rowing is great", "RO")`

Restituisce true.
