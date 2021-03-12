---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Scopri la funzione inSegment
feature: Percorsi
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 5%

---


# inSegment {#inSegment}

Controlla se una persona appartiene a un dato segmento.

>[!NOTE]
>
>Puoi recuperare fino a 100 segmenti.

Il nome del segmento deve essere una costante stringa. Non può essere un riferimento di campo né un&#39;espressione.

I segmenti sono definiti in [Adobe Experience Platform](https://platform.adobe.com/segment/overview). L’editor di espressioni fornisce un elenco di segmenti compilato automaticamente.

>[!NOTE]
>
>Solo i singoli utenti con gli stati di partecipazione al segmento **Realized** e **Esistenti** saranno considerati membri del segmento. Per ulteriori informazioni su come valutare un segmento, consulta la [documentazione del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

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
