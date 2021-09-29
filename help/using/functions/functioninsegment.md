---
product: adobe campaign
title: inSegment
description: Scopri la funzione inSegment
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: e56e6f5dcb8a4680851858355ac18a70bd832b73
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 6%

---

# inSegment {#inSegment}

Controlla se una persona appartiene a un dato segmento.

>[!NOTE]
>
>Puoi recuperare fino a 100 segmenti.

Il nome del segmento deve essere una costante stringa. Non può essere un riferimento di campo né un&#39;espressione.

I segmenti sono definiti in [Adobe Experience Platform](https://platform.adobe.com/segment/overview). L’editor di espressioni fornisce un elenco di segmenti compilato automaticamente.

I segmenti possono avere tre stati:

* esistente: l’entità continua a trovarsi nel segmento.
* realizzato: l’entità sta entrando nel segmento.
* usciti: entità in uscita dal segmento.

Solo i singoli utenti con gli stati di partecipazione al segmento **Realized** e **Esistenti** saranno considerati membri del segmento. Per ulteriori informazioni su come valutare un segmento, consulta la [documentazione del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

`IF inSegment('segmentName') == true` significa che hai un segmentMembership con lo stato inserito/esistente.

`ELSE inSegment('segmentName') == false` significa che hai un segmentMembership dello stato exited.

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
