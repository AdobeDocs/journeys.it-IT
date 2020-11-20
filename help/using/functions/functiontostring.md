---
product: adobe campaign
solution: Journey Orchestration
title: toString
description: Scopri la funzione toString
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 4%

---


# toString {#toString}

Converte un valore di argomento in un valore di stringa, a seconda del tipo. For more information on data types, refer to [this page](../expression/data-types.md).

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
