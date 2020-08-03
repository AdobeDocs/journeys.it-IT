---
title: toDuration
description: Scopri la funzione toDuration
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
source-wordcount: '277'
ht-degree: 1%

---


# toDuration {#toDuration}

Converte un valore di argomento in una durata. Per ulteriori informazioni sui tipi di dati, fare riferimento a [](../expression/data-types.md).

## Categoria

Conversione

## Sintassi delle funzioni

`toDuration(<parameter>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| string | formati basati sul formato di durata ISO-8601 PnDTnHnMn.nS con giorni considerati esattamente 24 ore |
| integer | numero di millisecondi |

Se espressione stringa: i formati accettati si basano sul formato di durata ISO-8601 PnDTnHnMn.nS con giorni considerati esattamente 24 ore.

La stringa inizia con un segno facoltativo, indicato dal simbolo ASCII negativo o positivo. Se negativo, l&#39;intero periodo viene ignorato. La lettera ASCII &quot;P&quot; è successiva in lettere maiuscole o minuscole. Ci sono quindi quattro sezioni, ciascuna costituita da un numero e un suffisso. Le sezioni hanno suffissi in ASCII di &quot;D&quot;, &quot;H&quot;, &quot;M&quot; e &quot;S&quot; per giorni, ore, minuti e secondi, accettati in lettere maiuscole o minuscole. I suffissi devono essere ordinati. La lettera ASCII &quot;T&quot; deve essere preceduta dalla prima occorrenza di un&#39;ora, un minuto o una seconda sezione. Almeno una delle quattro sezioni deve essere presente e, se è presente &quot;T&quot;, deve esserci almeno una sezione dopo la &quot;T&quot;. La parte numerica di ciascuna sezione deve essere costituita da una o più cifre ASCII. Il numero può essere preceduto dal simbolo ASCII negativo o positivo. Il numero di giorni, ore e minuti deve essere analizzato lungo. Il numero di secondi deve essere analizzato insieme alla frazione facoltativa. Il punto decimale può essere un punto o una virgola. La parte frazionaria può avere da zero a 9 cifre.

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
