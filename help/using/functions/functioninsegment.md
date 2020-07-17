---
title: inSegment
description: Scopri la funzione inSegment
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 4%

---


# inSegment {#inSegment}

Controlla se un singolo appartiene a un determinato segmento.

Il nome del segmento deve essere una costante stringa. Non può essere un riferimento a un campo né un&#39;espressione.

I segmenti sono definiti nel Adobe Experience Platform [](https://platform.adobe.com/segment/overview). L&#39;editor di espressioni fornisce un elenco di segmenti compilato automaticamente.

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

La funzione restituirà **[!UICONTROL true]** se l&#39;individuo all&#39;interno dell&#39;istanza di viaggio fa parte del segmento di Adobe Experience Platform  denominato &quot;men over 50&quot;, **[!UICONTROL false]** altrimenti.
