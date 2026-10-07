---
product: adobe campaign
title: Definizione del codice evento
description: Scopri come definire la chiave dell’evento
feature: Journeys
role: User
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 16%
---
# Definizione del codice evento {#concept_ond_hqt_52b}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._


La chiave è il campo o la combinazione di campi che fa parte dei dati di payload dell’evento e che consentirà al sistema di identificare la persona associata all’evento. La chiave può essere, ad esempio, Experience Cloud ID, un ID CRM o un indirizzo e-mail.

Se si intende sfruttare i dati memorizzati nel database Profilo cliente in tempo reale, è necessario selezionare come chiave evento le informazioni definite come identità di un profilo nel [Servizio profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it).

Consentirà al sistema di eseguire la riconciliazione tra l’evento e il profilo dell’individuo. Se selezioni uno schema con un&#39;identità primaria, i campi **[!UICONTROL Key]** e **[!UICONTROL Namespace]** sono precompilati. Se non è stata definita alcuna identità, verrà selezionata _identityMap > id_ come chiave primaria. Quindi devi selezionare uno spazio dei nomi e la chiave verrà precompilata (sotto il campo **[!UICONTROL Namespace]**) utilizzando _identityMap > id_.

Quando selezioni i campi, vengono taggati i campi di identità primari.

![](../assets/primary-identity.png)

Se devi utilizzare una chiave diversa, ad esempio un ID CRM o un indirizzo e-mail, devi aggiungerla manualmente:

1. Fare clic nel campo **[!UICONTROL Key]** o sull&#39;icona della matita.

   ![](../assets/journey16.png)

1. Seleziona il campo scelto come chiave nell’elenco dei campi del payload. Puoi anche passare all’editor di espressioni avanzate per creare chiavi più complesse (ad esempio, una concatenazione di due campi degli eventi). Vedi di seguito, in questa sezione.

   ![](../assets/journey20.png)

Quando l’evento viene ricevuto, il valore della chiave consente al sistema di identificare la persona associata all’evento. Associata a uno spazio dei nomi (vedi [questa pagina](../event/selecting-the-namespace.md)), la chiave può essere utilizzata per eseguire query in Adobe Experience Platform. Consulta [questa pagina](../building-journeys/about-orchestration-activities.md).
La chiave viene utilizzata anche per verificare che una persona appartenga a un percorso. Infatti, una persona non può trovarsi in due luoghi diversi nello stesso percorso. Di conseguenza, il sistema non consente che la stessa chiave, ad esempio la chiave CRMID=3224, si trovi in luoghi diversi nello stesso percorso.

È inoltre possibile accedere alle funzioni di espressione avanzate (**[!UICONTROL Advanced mode]**) se si desidera eseguire ulteriori manipolazioni. Queste funzioni ti consentono di manipolare i valori utilizzati per eseguire query specifiche, ad esempio per modificare i formati e eseguire concatenazioni di campi, tenendo conto solo di una parte di un campo (ad esempio i primi 10 caratteri). Consulta [questa pagina](../expression/expressionadvanced.md).
