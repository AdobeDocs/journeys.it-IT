---
product: adobe campaign
title: matchRegExp
description: Scopri la funzione matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 6%

---

# matchRegExp {#matchRegExp}

Restituisce true se la stringa nel primo parametro corrisponde all&#39;espressione regolare nel secondo parametro. Per ulteriori informazioni, consulta [questa pagina](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Categoria

Stringa

## Sintassi della funzione

`matchRegExp(<parameters>)`

## Elemento “parameters”

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
