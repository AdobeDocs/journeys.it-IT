---
product: adobe campaign
title: toDuration
description: Scopri la funzione toDuration
feature: Percorsi
role: Data Engineer
level: Experienced
exl-id: 77f068fa-678e-49a4-b45f-843c3287390a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 3%

---

# toDuration {#toDuration}

Converte un valore di argomento in una durata. Per ulteriori informazioni sui tipi di dati, consulta [questa pagina](../expression/data-types.md).

## Categoria

Conversione

## Sintassi della funzione

`toDuration(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| string | formati basati sul formato di durata ISO-8601 PnDTnHnMn.nS con giorni considerati esattamente 24 ore |
| integer | numero di millisecondi |

Espressione stringa If: I formati accettati sono basati sul formato di durata ISO-8601 PnDTnHnMn.nS con giorni considerati esattamente 24 ore.

La stringa inizia con un segno facoltativo, indicato dal simbolo ASCII negativo o positivo. Se negativo, l&#39;intero periodo viene negato. La lettera ASCII &quot;P&quot; è successiva in lettere maiuscole o minuscole. Ci sono poi quattro sezioni, ciascuna costituita da un numero e un suffisso. Le sezioni presentano suffissi in ASCII di &quot;D&quot;, &quot;H&quot;, &quot;M&quot; e &quot;S&quot; per giorni, ore, minuti e secondi, accettati in lettere maiuscole o minuscole. I suffissi devono essere ordinati. La lettera ASCII &quot;T&quot; deve essere preceduta dalla prima occorrenza, se presente, di un&#39;ora, di un minuto o di una seconda sezione. Almeno una delle quattro sezioni deve essere presente e se è presente &quot;T&quot; deve esserci almeno una sezione dopo la &quot;T&quot;. La parte numerica di ciascuna sezione deve essere costituita da una o più cifre ASCII. Il numero può essere preceduto dal simbolo ASCII negativo o positivo. Il numero di giorni, ore e minuti deve essere analizzato lungo. Il numero di secondi deve analizzare insieme alla frazione facoltativa. Il punto decimale può essere un punto o una virgola. La parte frazionaria può avere da zero a 9 cifre.

## Firme e tipo restituito

`toDuration(<string>)`

`toDuration(<integer>)`

Restituisce una durata.

## Esempi

`toDuration("PT10H")`

Restituisce la durata di 10 ore.

`toDuration("PT4S")`

Restituisce la durata di 4s.

`toDuration(4000)`

Restituisce la durata di 4s.
