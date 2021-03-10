---
product: adobe campaign
solution: Journey Orchestration
title: Definizione del codice evento
description: Scopri come definire la chiave evento
feature: Percorsi
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 5%

---


# Definizione del codice evento {#concept_ond_hqt_52b}

La chiave è il campo o la combinazione di campi che fa parte dei dati di payload dell’evento e che consentirà al sistema di identificare la persona associata all’evento. La chiave può essere, ad esempio, l&#39;ID Experience Cloud, un ID CRM o un indirizzo e-mail.

Se prevedi di sfruttare i dati memorizzati nel database Profilo cliente in tempo reale, devi selezionare, come chiave evento, le informazioni definite come identità del profilo nel [Servizio Profilo cliente in tempo reale](https://docs.adobe.com/content/help/it-IT/experience-platform/profile/home.html).

Consentirà al sistema di eseguire la riconciliazione tra l’evento e il profilo del singolo utente. Se selezioni uno schema con un&#39;identità primaria, i campi **[!UICONTROL Key]** e **[!UICONTROL Namespace]** sono precompilati. Se non è definita alcuna identità, selezioniamo _identityMap > id_ come chiave primaria. Quindi devi selezionare uno spazio dei nomi e la chiave verrà precompilata (sotto il campo **[!UICONTROL Namespace]** ) utilizzando _identityMap > id_.

Durante la selezione dei campi, i campi di identità principali vengono contrassegnati con tag.

![](../assets/primary-identity.png)

Se devi utilizzare una chiave diversa, ad esempio un ID CRM o un indirizzo e-mail, devi aggiungerla manualmente:

1. Fai clic all’interno del campo **[!UICONTROL Key]** o sull’icona della matita.

   ![](../assets/journey16.png)

1. Seleziona il campo scelto come chiave nell’elenco dei campi payload. Puoi anche passare all’editor di espressioni avanzate per creare chiavi più complesse (ad esempio, una concatenazione di due campi degli eventi). Vedi sotto, in questa sezione.

   ![](../assets/journey20.png)

Quando l’evento viene ricevuto, il valore della chiave consentirà al sistema di identificare la persona associata all’evento. Associata a uno spazio dei nomi (consulta [questa pagina](../event/selecting-the-namespace.md)), può essere utilizzata per eseguire query su Adobe Experience Platform. Consulta [questa pagina](../building-journeys/about-orchestration-activities.md).
La chiave viene utilizzata anche per verificare che una persona si trovi in un percorso. Infatti, una persona non può trovarsi in due luoghi diversi nello stesso percorso. Di conseguenza, il sistema non consente che la stessa chiave, ad esempio la chiave CRMID=3224, si trovi in luoghi diversi nello stesso percorso.

Puoi anche accedere alle funzioni di espressione avanzate (**[!UICONTROL Advanced mode]**) per eseguire ulteriori manipolazioni. Queste funzioni consentono di manipolare i valori utilizzati per eseguire query specifiche, ad esempio la modifica dei formati, l’esecuzione di concatenazioni di campi, tenendo conto solo di una parte di un campo (ad esempio i 10 primi caratteri). Consulta [questa pagina](../expression/expressionadvanced.md).
