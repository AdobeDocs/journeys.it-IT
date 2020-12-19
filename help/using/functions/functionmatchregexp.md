---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: Scopri la funzione matchRegExp
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 4%

---


# matchRegExp {#matchRegExp}

Restituisce true se la stringa nel primo parametro corrisponde all&#39;espressione regolare nel secondo parametro. Per ulteriori informazioni, vedere [questa pagina](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

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
