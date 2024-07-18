---
product: adobe campaign
title: toDuration
description: Scopri la funzione toDuration
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 77f068fa-678e-49a4-b45f-843c3287390a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
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

## Elemento “parameters”

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
