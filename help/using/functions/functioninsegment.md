---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Scopri la funzione inSegment
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 7%

---


# inSegment {#inSegment}

Controlla se una persona appartiene a un dato segmento.

Il nome del segmento deve essere una costante stringa. Non può essere un riferimento di campo né un&#39;espressione.

I segmenti sono definiti in [Adobe Experience Platform](https://platform.adobe.com/segment/overview). L’editor di espressioni fornisce un elenco di segmenti compilato automaticamente.

>[!NOTE]
>
>Puoi recuperare fino a 100 segmenti.

## Categoria

Adobe Experience Platform

## Sintassi della funzione

`inSegment(<parameter>)`

## Parametri

| Parametro | Descrizione | Tipo |
|--- |--- |--- |
| Segmento | Nome del segmento | `<string>` |

## Firma e tipo restituito

`inSegment(<string>)`

Restituisce un valore booleano.

## Esempio

`inSegment("men over 50")`

Spiegazione:

La funzione restituirà **[!UICONTROL true]** se la persona all&#39;interno dell&#39;istanza del percorso fa parte del segmento Adobe Experience Platform denominato &quot;men over 50&quot;, **[!UICONTROL false]** in caso contrario.
