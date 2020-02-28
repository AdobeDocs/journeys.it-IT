---
title: Selezione dello spazio dei nomi
description: Scopri come selezionare lo spazio dei nomi
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
source-git-commit: 411ecf0ec4dc6a87c4e129b40f2918799bef54bf

---


# Selezione dello spazio dei nomi {#concept_ckb_3qt_52b}

Lo spazio dei nomi consente di definire il tipo di chiave utilizzata per identificare la persona associata all&#39;evento. La configurazione è opzionale. È necessario per recuperare, nei viaggi, informazioni aggiuntive provenienti dal profilo [cliente](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)in tempo reale. La definizione dello spazio nomi non è necessaria se si utilizzano solo dati provenienti da un sistema di terze parti tramite un&#39;origine dati personalizzata.

È possibile utilizzare uno dei predefiniti oppure crearne uno nuovo utilizzando il servizio Spazio nomi identità. Fare riferimento a questa [pagina](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_namespace_overview/identity_namespace_overview.md).

Se si seleziona uno schema con un&#39;identità primaria, i campi **[!UICONTROL Key]** e **[!UICONTROL Namespace]** vengono precompilati. Se non è definita alcuna identità, come chiave primaria selezioneremo _identityMap > id_ . Quindi è necessario selezionare uno spazio nomi e la chiave sarà precompilata (sotto il **[!UICONTROL Namespace]** campo) utilizzando _identityMap > id_.

Quando si selezionano i campi, i tag dei campi identità primari sono assegnati.

![](../assets/primary-identity.png)


Selezionare uno spazio nomi dall&#39;elenco a discesa.

![](../assets/journey17.png)

È consentito un solo spazio dei nomi per percorso. Se si utilizzano più eventi nello stesso percorso, è necessario che utilizzino lo stesso spazio nomi. Vedere [](../building-journeys/journey.md).
