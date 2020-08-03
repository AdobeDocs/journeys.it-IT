---
title: matchRegExp
description: Scopri la funzione matchRegExp
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 3%

---


# matchRegExp {#matchRegExp}

Restituisce true se la stringa nel primo parametro corrisponde all&#39;espressione regolare nel secondo parametro. Per ulteriori informazioni, consultate [questa pagina](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Categoria

Stringa

## Sintassi delle funzioni

`matchRegExp(<parameters>)`

## Parametri

| Parametro | Tipo |
|--- |--- |
| string | string |
| regexp | string |

## Firma e tipo restituito

`matchRegExp(<string>,<string>)`

Restituisce un valore true.

## Esempio

`matchRegExp("Hello World", "Hello\s+World")`

Restituisce true.

Spiegazione:

Qui si verifica se la stringa soddisfa l&#39;espressione regolare (sintassi Java): inizia con &quot;Hello&quot;, poi qualsiasi tipo di stringa e finiture con &quot;World&quot;.
