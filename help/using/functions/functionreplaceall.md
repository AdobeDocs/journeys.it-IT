---
title: replaceAll
description: Scopri la funzione replaceAll
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
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
