---
product: adobe campaign
title: toDuration
description: Scopri la funzione toDuration
feature: Journeys
role: Developer
level: Experienced
exl-id: 77f068fa-678e-49a4-b45f-843c3287390a
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 3%
---
# toDuration {#toDuration}

Converte un valore di argomento in una durata. Per ulteriori informazioni sui tipi di dati, consultare [questa pagina](../expression/data-types.md).

## Categoria

Conversione

## Sintassi della funzione

`toDuration(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| stringa | formati basati sul formato di durata ISO-8601 PnDTnHnMn.nS con giorni considerati esattamente 24 ore |
| intero | numero di millisecondi |

Espressione stringa: i formati accettati sono basati sul formato di durata ISO-8601 PnDTnHnMn.nS con giorni considerati esattamente 24 ore.

La stringa inizia con un segno facoltativo, indicato dal simbolo ASCII negativo o positivo. Se negativo, l&#39;intero periodo viene ignorato. La lettera ASCII &quot;P&quot; è successiva in maiuscolo o in minuscolo. Ci sono poi quattro sezioni, ciascuna composta da un numero e un suffisso. Le sezioni hanno suffissi in ASCII di &quot;D&quot;, &quot;H&quot;, &quot;M&quot; e &quot;S&quot; per giorni, ore, minuti e secondi, accettati in maiuscolo o minuscolo. I suffissi devono essere disposti in ordine. La lettera ASCII &quot;T&quot; deve precedere la prima occorrenza, se presente, di un&#39;ora, un minuto o una seconda sezione. Deve essere presente almeno una delle quattro sezioni e, se &quot;T&quot; è presente, deve esserci almeno una sezione dopo la &quot;T&quot;. La parte numerica di ogni sezione deve essere costituita da una o più cifre ASCII. Il numero può essere preceduto dal simbolo ASCII negativo o positivo. Il numero di giorni, ore e minuti deve essere analizzato in lungo. Il numero di secondi deve essere analizzato insieme alla frazione facoltativa. Il punto decimale può essere un punto o una virgola. La parte frazionaria può avere da zero a 9 cifre.

## Firme e tipo restituito

`toDuration(<string>)`

`toDuration(<integer>)`

Restituisce una durata.

## Esempi

`toDuration("PT10H")`

Restituisce una durata di 10 ore.

`toDuration("PT4S")`

Restituisce una durata di 4 secondi.

`toDuration(4000)`

Restituisce una durata di 4 secondi.
