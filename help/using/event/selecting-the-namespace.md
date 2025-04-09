---
product: adobe campaign
title: Selezione dello spazio dei nomi
description: Scopri come selezionare lo spazio dei nomi
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 5%

---

# Selezione dello spazio dei nomi {#concept_ckb_3qt_52b}


>[!CAUTION]
>
>**Cerchi Adobe Systems Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy sostituiti da Journey Optimizer. Contatta il tuo team account se hai domande sulle accesso a Journey Orchestration o Journey Optimizer._


Lo spazio nomi consente di definire il tipo di chiave utilizzata per identificare la persona associata all&#39;evento. La sua configurazione è facoltativa. È necessario se vuoi recuperare, nei tuoi viaggi, informazioni aggiuntive provenienti dal [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it). La definizione dello spazio dei nomi non è necessaria se si utilizzano solo dati provenienti da un sistema di terze parti tramite un&#39;origine dati personalizzata.

È possibile utilizzare uno di quelli predefiniti o crearne uno nuovo utilizzando il servizio Spazio dei nomi Identity. Fare riferimento a questa [pagina](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it).

Se si seleziona uno schema con un&#39;identità primaria, i **[!UICONTROL Key]** campi e **[!UICONTROL Namespace]** sono precompilati. Se non è definita alcuna identità, selezioniamo _identityMap > id_ come chiave primaria. Poi devi selezionare un namespace e la chiave sarà precompilata (sotto il **[!UICONTROL Namespace]** campo) utilizzando _identityMap > id_.

Quando si selezionano i campi, i campi di identità primari vengono taggato.

![](../assets/primary-identity.png)


Seleziona un namespace dall&#39;elenco a discesa.

![](../assets/journey17.png)

È consentito un solo namespace per viaggio. Se utilizzi più eventi nello stesso percorso, questi devono usare lo stesso namespace. Consulta [questa pagina](../building-journeys/journey.md).
