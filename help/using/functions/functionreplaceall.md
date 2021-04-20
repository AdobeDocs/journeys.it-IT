---
product: adobe campaign
solution: Journey Orchestration
title: replaceAll
description: Scopri la funzione replaceAll
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 6%

---


# replaceAll {#replaceAll}

Sostituisce tutte le occorrenze corrispondenti alla stringa di destinazione con la stringa di sostituzione nella stringa di base.

La sostituzione procede dall’inizio della stringa alla fine, ad esempio sostituendo &quot;aa&quot; con &quot;b&quot; nella stringa &quot;aaa&quot; si otterrà &quot;ba&quot; invece di &quot;ab&quot;.

## Categoria

Stringa

## Sintassi della funzione

`replaceAll(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|--------------|
| base | string |
| target | string |
| sostituzione | string |

## Firma e tipo restituito

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Restituisce una stringa.

## Esempio

`replaceAll("Hello World", "l", "x")`

Restituisce &quot;Hexxo Worxd&quot;.
