---
product: adobe campaign
title: toString
description: Scopri la funzione toString
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# toString {#toString}

Converte un valore di argomento in un valore di stringa, a seconda del tipo. Per ulteriori informazioni sui tipi di dati, consulta [questa pagina](../expression/data-types.md).

## Categoria

Conversione

## Sintassi della funzione

`toString(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| dateTime | converte la data in formato data UTC |
| dateTimeOnly | converte la data in formato data UTC |
| durata | convertire nel numero corrispondente di millisecondi come stringa |
| fuso orario | converti nella rappresentazione stringa id fuso orario (JODA id) |
| integer | converte in rappresentazione stringa del valore (1 diventa &quot;1&quot;) |
| decimale | converte in rappresentazione stringa del valore (1.5 diventa &quot;1.5&quot;) |
| booleano | converte il valore booleano come &#39;true&#39; se true, &#39;false&#39; se false |

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
