---
product: adobe campaign
title: endWithIgnoreCase
description: Scopri la funzione endWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 18%

---

# endWithIgnoreCase {#endWithIgnoreCase}

Controlla se la stringa del primo argomento termina con una stringa specifica (stringa del secondo argomento), senza tenere conto delle maiuscole/minuscole.

## Categoria

Stringa

## Sintassi della funzione

`endWithIgnoreCase(<parameters>)`

## Elemento “parameters”

| Parametro | Tipo |
|-----------|------------------|
| stringa | stringa |
| suffisso | stringa |

## Firma e tipo restituito

`endWithIgnoreCase(<string>,<string>)`

Restituisce un valore booleano.

## Esempio

`endWithIgnoreCase("rowing is great", "AT")`

Restituisce true.
