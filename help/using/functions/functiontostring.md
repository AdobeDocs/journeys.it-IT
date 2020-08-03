---
title: toString
description: Scopri la funzione toString
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
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 2%

---


# toString {#toString}

Converte un valore di argomento in un valore di stringa, a seconda del tipo. Per ulteriori informazioni sui tipi di dati, fare riferimento a [](../expression/data-types.md).

## Categoria

Conversione

## Sintassi delle funzioni

`toString(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| dateTime | converte la data in formato data UTC |
| dateTimeOnly | converte la data in formato data UTC |
| length | converti nel numero corrispondente di millisecondi come stringa |
| fuso orario | converti in rappresentazione stringa id fuso orario (JODA id) |
| integer | converte in rappresentazione stringa del valore (1 diventa &quot;1&quot;) |
| decimal | converte in rappresentazione stringa del valore (1.5 diventa &quot;1.5&quot;) |
| boolean | converte il valore booleano come &#39;true&#39; se true, &#39;false&#39; se false |

## Firme e tipo restituito

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Restituisce una stringa.

## Esempio

`toString(4)`

Restituisce &quot;4&quot;.
