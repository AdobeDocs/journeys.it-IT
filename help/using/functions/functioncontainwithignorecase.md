---
product: adobe campaign
title: containWithIgnoreCase
description: Scopri la funzione containWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 12%

---

# containWithIgnoreCase {#containWithIgnoreCase}

Controlla se la seconda stringa di argomento è contenuta nella prima stringa di argomento, senza tenere conto del caso.

## Categoria

Stringa

## Sintassi della funzione

`containWithIgnoreCase(<parameters>)`

## Elemento “parameters”

| Parametro | Tipo |
|-----------|------------------|
| string | string |
| ricerca stringa | string |

## Firma e tipo restituito

`containWithIgnoreCase(<string>,<string>)`

Restituisce un valore booleano.

## Esempio

`containWithIgnoreCase("rowing is great', "GREAT")`

Restituisce true.
