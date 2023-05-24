---
product: adobe campaign
title: Definizione del codice evento
description: Scopri come definire la chiave dell’evento
feature: Journeys
role: User
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 5%

---

# Definizione del codice evento {#concept_ond_hqt_52b}

La chiave è il campo o la combinazione di campi che fa parte dei dati di payload dell’evento e che consentirà al sistema di identificare la persona associata all’evento. La chiave può essere, ad esempio, l’ID Experience Cloud, un ID del sistema di gestione delle relazioni con i clienti o un indirizzo e-mail.

Se prevedi di sfruttare i dati memorizzati nel database Real-time Customer Profile, devi selezionare, come chiave evento, le informazioni definite come identità di un profilo in [Servizio Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it).

Consentirà al sistema di eseguire la riconciliazione tra l’evento e il profilo dell’individuo. Se selezioni uno schema con un’identità primaria, il **[!UICONTROL Key]** e **[!UICONTROL Namespace]** i campi sono precompilati. Se non è stata definita alcuna identità, selezioniamo _identityMap > id_ come chiave primaria. Quindi devi selezionare uno spazio dei nomi e la chiave verrà precompilata (sotto il **[!UICONTROL Namespace]** field) utilizzando _identityMap > id_.

Quando selezioni i campi, vengono taggati i campi di identità primari.

![](../assets/primary-identity.png)

Se devi utilizzare una chiave diversa, ad esempio un ID CRM o un indirizzo e-mail, devi aggiungerla manualmente:

1. Fai clic all’interno del **[!UICONTROL Key]** o sull’icona della matita.

   ![](../assets/journey16.png)

1. Seleziona il campo scelto come chiave nell’elenco dei campi del payload. Puoi anche passare all’editor di espressioni avanzate per creare chiavi più complesse (ad esempio, una concatenazione di due campi degli eventi). Vedi di seguito, in questa sezione.

   ![](../assets/journey20.png)

Quando l’evento viene ricevuto, il valore della chiave consente al sistema di identificare la persona associata all’evento. Associato a uno spazio dei nomi (vedere [questa pagina](../event/selecting-the-namespace.md)), la chiave può essere utilizzata per eseguire query sul Adobe Experience Platform. Consulta [questa pagina](../building-journeys/about-orchestration-activities.md).
La chiave viene utilizzata anche per verificare che una persona appartenga a un percorso. Infatti, una persona non può trovarsi in due luoghi diversi nello stesso percorso. Di conseguenza, il sistema non consente che la stessa chiave, ad esempio la chiave CRMID=3224, si trovi in luoghi diversi nello stesso percorso.

È inoltre possibile accedere alle funzioni di espressione avanzate (**[!UICONTROL Advanced mode]**) se desideri eseguire ulteriori manipolazioni. Queste funzioni ti consentono di manipolare i valori utilizzati per eseguire query specifiche, ad esempio per modificare i formati e eseguire concatenazioni di campi, tenendo conto solo di una parte di un campo (ad esempio i primi 10 caratteri). Consulta [questa pagina](../expression/expressionadvanced.md).
