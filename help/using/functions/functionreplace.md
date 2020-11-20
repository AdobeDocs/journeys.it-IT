---
product: adobe campaign
solution: Journey Orchestration
title: replace
description: Ulteriori informazioni sulla sostituzione della funzione
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 5%

---


# replace {#replace}

Sostituisce la prima occorrenza che corrisponde alla stringa di destinazione con la stringa sostitutiva nella stringa base.

Il passaggio di sostituzione procede dall&#39;inizio della stringa alla fine, ad esempio, sostituendo &quot;aa&quot; con &quot;b&quot; nella stringa &quot;aaa&quot; si ottiene &quot;ba&quot; anziché &quot;ab&quot;.

## Categoria

Stringa

## Sintassi delle funzioni

`replace(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|--------------|
| base | string |
| target | string |
| sostitutivo | string |

## Firma e tipo restituito

`replace(<base>,<target>,<replacement>)`

Restituisce una stringa.

## Esempio

`replace("Hello World", "l", "x")`

Restituisce &quot;Hexlo World&quot;.
