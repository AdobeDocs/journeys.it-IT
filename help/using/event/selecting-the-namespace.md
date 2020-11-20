---
product: adobe campaign
solution: Journey Orchestration
title: Selezione dello spazio dei nomi
description: Scoprite come selezionare lo spazio dei nomi
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 12%

---


# Selezione dello spazio dei nomi {#concept_ckb_3qt_52b}

Lo spazio dei nomi consente di definire il tipo di chiave utilizzata per identificare la persona associata all&#39;evento. La configurazione è opzionale. È necessario per recuperare, nei viaggi, informazioni aggiuntive provenienti dal profilo [cliente](https://docs.adobe.com/content/help/it-IT/experience-platform/profile/home.html)in tempo reale. La definizione dello spazio dei nomi non è necessaria se si utilizzano solo dati provenienti da un sistema di terze parti tramite un&#39;origine dati personalizzata.

È possibile utilizzare uno dei predefiniti oppure crearne uno nuovo utilizzando il servizio Spazio nomi identità. Refer to this [page](https://docs.adobe.com/content/help/it-IT/experience-platform/identity/home.html).

Se si seleziona uno schema con un&#39;identità primaria, i campi **[!UICONTROL Key]** e **[!UICONTROL Namespace]** vengono precompilati. Se non è definita alcuna identità, come chiave primaria selezioneremo _identityMap > id_ . Quindi è necessario selezionare uno spazio dei nomi e la chiave sarà precompilata (sotto il **[!UICONTROL Namespace]** campo) utilizzando _identityMap > id_.

Quando si selezionano i campi, i tag dei campi identità primari sono assegnati.

![](../assets/primary-identity.png)


Selezionare uno spazio nomi dall&#39;elenco a discesa.

![](../assets/journey17.png)

Per ogni percorso è consentito un solo spazio dei nomi. Se si utilizzano più eventi nello stesso percorso, è necessario che utilizzino lo stesso spazio nomi. Consulta [questa pagina](../building-journeys/journey.md).
