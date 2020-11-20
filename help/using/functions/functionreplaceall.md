---
product: adobe campaign
solution: Journey Orchestration
title: replaceAll
description: Scopri la funzione replaceAll
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%

---


# replaceAll {#replaceAll}

Sostituisce tutte le occorrenze che corrispondono alla stringa di destinazione con la stringa sostitutiva nella stringa base.

Il passaggio di sostituzione procede dall&#39;inizio della stringa alla fine, ad esempio, sostituendo &quot;aa&quot; con &quot;b&quot; nella stringa &quot;aaa&quot; si ottiene &quot;ba&quot; anziché &quot;ab&quot;.

## Categoria

Stringa

## Sintassi delle funzioni

`replaceAll(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|--------------|
| base | string |
| target | string |
| sostitutivo | string |

## Firma e tipo restituito

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Restituisce una stringa.

## Esempio

`replaceAll("Hello World", "l", "x")`

Restituisce &quot;Hexxo Worxd&quot;.
