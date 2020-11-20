---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: Scopri la funzione nowWithDelta
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 4%

---


# nowWithDelta {#nowWithDelta}

Restituisce il valore datetime corrente, incluso un offset. Se viene specificato un ID del fuso orario, verrà applicato l&#39;offset del fuso orario. For more information on data types, refer to [this page](../expression/data-types.md).

## Categoria

Data

## Sintassi delle funzioni

`nowWithDelta(<parameters>)`

## Parametri

| Parametro | Descrizione |
|--- |--- |
| delta | valore intero positivo o negativo |
| data part | anni, mesi, giorni, ore, minuti o secondi come stringa |
| id fuso orario | rappresentazione in formato stringa del valore del fuso orario. Per ulteriori informazioni, consulta Tipi [](../expression/data-types.md)di dati. L&#39;ID del fuso orario deve essere una costante stringa. Non può essere un riferimento a un campo né un&#39;espressione. |

## Firme e tipo restituito

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Restituisce un dateTime.

## Esempi

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Restituisce un dateTime esattamente 2 ore fa.
