---
product: adobe campaign
title: inSegment
description: Scopri la funzione in Segment
feature: Journeys
role: Developer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
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
source-wordcount: '202'
ht-degree: 5%
---
# inSegment {#inSegment}

Controlla se un singolo appartiene a un dato segmento.

>[!NOTE]
>
>Puoi recuperare fino a 100 segmenti.

Il nome del segmento deve essere una costante stringa. Non può essere un riferimento di campo né un&#39;espressione.

I segmenti sono definiti in [Adobe Experience Platform](https://platform.adobe.com/segment/overview). L’editor espressioni fornisce un elenco di segmenti completato automaticamente.

I segmenti possono avere tre stati:

* esistente: l’entità continua a essere nel segmento.
* realizzato: l’entità sta entrando nel segmento.
* uscita: l’entità sta uscendo dal segmento.

Solo i singoli utenti con gli stati di partecipazione al segmento **Realizzato** e **Esistente** verranno considerati membri del segmento. Per ulteriori informazioni su come valutare un segmento, consulta la [documentazione del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

`IF inSegment('segmentName') == true` significa che hai un segmentMembership con lo stato inserito/esistente.

`ELSE inSegment('segmentName') == false` significa che hai un segmentMembership con stato di uscita.

## Categoria

Adobe Experience Platform

## Sintassi della funzione

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

La funzione restituirà **[!UICONTROL true]** se l&#39;individuo all&#39;interno dell&#39;istanza del percorso fa parte del segmento Adobe Experience Platform denominato &quot;men over 50&quot;, **[!UICONTROL false]** in caso contrario.
