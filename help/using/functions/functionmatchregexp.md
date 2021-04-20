---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: Scopri la funzione matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 5%

---


# matchRegExp {#matchRegExp}

Restituisce true se la stringa nel primo parametro corrisponde all&#39;espressione regolare nel secondo parametro. Per ulteriori informazioni, consulta [questa pagina](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Categoria

Stringa

## Sintassi della funzione

`matchRegExp(<parameters>)`

## Parametri

| Parametro | Tipo |
|--- |--- |
| string | string |
| rigexp | string |

## Firma e tipo restituito

`matchRegExp(<string>,<string>)`

Restituisce un valore true.

## Esempio

`matchRegExp("Hello World", "Hello\s+World")`

Restituisce true.

Spiegazione:

Qui si controlla se la stringa soddisfa l&#39;espressione regolare (sintassi java): inizia con &quot;Hello&quot;, poi qualsiasi tipo di stringa e finisce con &quot;World&quot;.
