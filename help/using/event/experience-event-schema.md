---
product: adobe campaign
solution: Journey Orchestration
title: 'Informazioni sugli schemi ExperienceEvent per gli eventi di Journey Orchestration '
description: 'Scopri gli schemi ExperienceEvent per gli eventi di Journey Orchestration '
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---



# Informazioni sugli schemi ExperienceEvent per gli eventi [!DNL Journey Orchestration]

[!DNL Journey Orchestration] gli eventi sono eventi di esperienza XDM che vengono inviati all&#39;Adobe Experience Platform tramite Streaming Ingestion.

Di conseguenza, un prerequisito importante per impostare gli eventi per [!DNL Journey Orchestration] è che tu abbia familiarità con il modello dati esperienza (o XDM) di Adobe Experience Platform e con come comporre gli schemi evento esperienza XDM, nonché con come trasmettere i dati in formato XDM all&#39;Adobe Experience Platform.

## Requisiti dello schema per gli eventi [!DNL Journey Orchestration]

Il primo passaggio nella configurazione di un evento per [!DNL Journey Orchestration] consiste nell&#39;assicurarsi di disporre di uno schema XDM definito per rappresentare l&#39;evento, e di un dataset creato per registrare le istanze dell&#39;evento sull&#39;Adobe Experience Platform. La disponibilità di un set di dati per gli eventi non è strettamente necessaria, ma l&#39;invio degli eventi a un set di dati specifico vi consentirà di mantenere la cronologia degli eventi degli utenti per riferimento e analisi futuri, pertanto è sempre una buona idea. Se non si dispone già di uno schema e di un set di dati adeguati per l&#39;evento, entrambe le operazioni possono essere eseguite nell&#39;interfaccia Web di Adobe Experience Platform.

![](../assets/schema1.png)

Qualsiasi schema XDM che verrà utilizzato per gli eventi [!DNL Journey Orchestration] deve soddisfare i seguenti requisiti:

* Lo schema deve essere della classe ExperienceEvent XDM.

   ![](../assets/schema2.png)

* Per gli eventi generati dal sistema, lo schema deve includere il mixin eventID di orchestrazione. [!DNL Journey Orchestration] utilizza questo campo per identificare gli eventi utilizzati nei viaggi.

   ![](../assets/schema3.png)

* Dichiarare un campo di identità per identificare l’oggetto dell’evento. Se non viene specificata alcuna identità, è possibile utilizzare una mappa di identità. Questo non è consigliato.

   ![](../assets/schema4.png)

* Se si desidera che questi dati siano disponibili per la ricerca successiva in un viaggio, contrassegnare lo schema e il dataset per il profilo.

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* Potete includere campi di dati per acquisire qualsiasi altro dato contestuale da includere nell&#39;evento, ad esempio informazioni sull&#39;utente, sul dispositivo da cui è stato generato l&#39;evento, sulla posizione o su qualsiasi altra circostanza significativa correlata all&#39;evento.

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)