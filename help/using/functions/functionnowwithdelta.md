---
title: nowWithDelta
description: Scopri la funzione nowWithDelta
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

---


# nowWithDelta {#nowWithDelta}

Restituisce il valore datetime corrente, incluso un offset. Se viene specificato un ID del fuso orario, verrà applicato l&#39;offset del fuso orario. Per ulteriori informazioni sui tipi di dati, fare riferimento a [](../expression/data-types.md).

## Categoria

Data

## Sintassi funzione

`nowWithDelta(<parameters>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| delta | valore intero positivo o negativo |
| data part | anni, mesi, giorni, ore, minuti o secondi come stringa |
| id fuso orario | rappresentazione stringa del valore del fuso orario. Per ulteriori informazioni, consulta [](../expression/data-types.md). L&#39;ID del fuso orario deve essere una costante stringa. Non può essere un riferimento a un campo né un&#39;espressione. |

## Firme e tipo restituito

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Restituisce un dateTime.

## Esempi

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Restituisce un dateTime esattamente 2 ore fa.
