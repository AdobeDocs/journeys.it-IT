---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: Scopri la funzione containWithIgnoreCase
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 9%

---


# containWithIgnoreCase {#containWithIgnoreCase}

Controlla se la seconda stringa di argomento è contenuta nella prima stringa di argomento, senza tenere conto del caso.

## Categoria

Stringa

## Sintassi della funzione

`containWithIgnoreCase(<parameters>)`

## Parametri

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
