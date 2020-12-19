---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Scopri la funzione inSegment
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 6%

---


# inSegment {#inSegment}

Controlla se un singolo appartiene a un determinato segmento.

Il nome del segmento deve essere una costante stringa. Non può essere un riferimento a un campo né un&#39;espressione.

I segmenti sono definiti in [Adobe Experience Platform](https://platform.adobe.com/segment/overview). L&#39;editor di espressioni fornisce un elenco di segmenti compilato automaticamente.

>[!NOTE]
>
>Puoi recuperare fino a 100 segmenti.

## Categoria

Adobe Experience Platform

## Sintassi delle funzioni

`inSegment(<parameter>)`

## Parametri

| Parametro | Descrizione | Tipo |
|--- |--- |--- |
| Segmento | Il nome del segmento | `<string>` |

## Firma e tipo restituito

`inSegment(<string>)`

Restituisce un valore booleano.

## Esempio

`inSegment("men over 50")`

Spiegazione:

La funzione restituirà **[!UICONTROL true]** se l&#39;individuo all&#39;interno dell&#39;istanza del viaggio fa parte del segmento Adobe Experience Platform denominato &quot;men over 50&quot;, **[!UICONTROL false]** in caso contrario.
