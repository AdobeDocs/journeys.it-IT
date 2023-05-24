---
product: adobe campaign
title: toString
description: Scopri la funzione toString
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: c7730ecac062719e5e5adfd465d1cedb59b3eaf1
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 10%

---

# toString {#toString}

Converte un valore di argomento in un valore stringa, a seconda del tipo. Per ulteriori informazioni sui tipi di dati, consulta [questa pagina](../expression/data-types.md).

## Categoria

Conversione

## Sintassi della funzione

`toString(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| dateTime | converte la data nel formato data UTC |
| dateTimeOnly | converte la data nel formato data UTC |
| durata | convertire nel numero di millisecondi corrispondente come stringa |
| numero intero | converte in rappresentazione stringa del valore (1 diventa &quot;1&quot;) |
| decimal | converte in rappresentazione stringa del valore (1,5 diventa &quot;1,5&quot;) |
| booleano | converti il valore booleano come &#39;true&#39; se true, &#39;false&#39; se false |

## Firme e tipo restituito

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Restituisce una stringa.

## Esempio

`toString(4)`

Restituisce &quot;4&quot;.
