---
product: adobe campaign
title: Selezione dello spazio dei nomi
description: Scopri come selezionare lo spazio dei nomi
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 10%

---

# Selezione dello spazio dei nomi {#concept_ckb_3qt_52b}

Lo spazio dei nomi ti consente di definire il tipo di chiave utilizzata per identificare la persona associata all’evento. La configurazione è facoltativa. È necessario se desideri recuperare, nei tuoi percorsi, informazioni aggiuntive provenienti dalla [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it). La definizione dello spazio dei nomi non è necessaria se utilizzi solo dati provenienti da un sistema di terze parti tramite un’origine dati personalizzata.

È possibile utilizzare uno dei predefiniti oppure crearne uno nuovo utilizzando il servizio Namespace Identity. Fai riferimento a questo [page](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it).

Se selezioni uno schema con un&#39;identità principale, la **[!UICONTROL Key]** e **[!UICONTROL Namespace]** i campi sono precompilati. Se non è definita alcuna identità, selezioniamo _identityMap > id_ come chiave primaria. Quindi devi selezionare uno spazio dei nomi e la chiave verrà precompilata (sotto la **[!UICONTROL Namespace]** campo) utilizzando _identityMap > id_.

Durante la selezione dei campi, i campi di identità principali vengono contrassegnati con tag.

![](../assets/primary-identity.png)


Seleziona uno spazio dei nomi dall’elenco a discesa.

![](../assets/journey17.png)

È consentito un solo spazio dei nomi al percorso. Se utilizzi più eventi nello stesso percorso, devi utilizzare lo stesso namespace. Consulta [questa pagina](../building-journeys/journey.md).
