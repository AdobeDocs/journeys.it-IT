---
title: 'Informazioni sugli schemi ExperienceEvent per gli eventi di orchestrazione del viaggio '
description: 'Scopri gli schemi ExperienceEvent per gli eventi di orchestrazione del viaggio '
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
source-git-commit: 9b8d4bebe024e90733cb1ae6d31b36fb6ce4b606

---



# Informazioni sugli schemi ExperienceEvent per gli eventi di orchestrazione del viaggio

Gli eventi di orchestrazione del percorso sono eventi esperienza XDM inviati ad Adobe Experience Platform tramite Streaming Ingestion.

Di conseguenza, un prerequisito importante per configurare gli eventi per l&#39;orchestrazione del viaggio è che si abbia familiarità con il modello dati esperienza (o XDM) della piattaforma e con come comporre gli schemi evento esperienza XDM, nonché con come trasmettere i dati in formato XDM alla piattaforma.

## Requisiti dello schema per gli eventi di orchestrazione del viaggio

Il primo passaggio nella configurazione di un evento per l&#39;orchestrazione del percorso consiste nell&#39;assicurarsi che sia impostato uno schema XDM per rappresentare l&#39;evento, e che sia creato un dataset per registrare le istanze dell&#39;evento sulla piattaforma. La disponibilità di un set di dati per gli eventi non è strettamente necessaria, ma l&#39;invio degli eventi a un set di dati specifico vi consentirà di mantenere la cronologia degli eventi degli utenti per riferimento e analisi futuri, pertanto è sempre una buona idea. Se non disponete già di uno schema e di un set di dati adeguati per l&#39;evento, entrambi i task possono essere eseguiti nell&#39;interfaccia Web della piattaforma.

![](../assets/schema1.png)

Qualsiasi schema XDM che verrà utilizzato per gli eventi di orchestrazione del percorso deve soddisfare i seguenti requisiti:

* Lo schema deve essere della classe ExperienceEvent XDM.

![](../assets/schema2.png)

* Lo schema deve includere il mixin eventID di orchestrazione. L&#39;orchestrazione del percorso utilizza questo campo per identificare gli eventi utilizzati nei viaggi.

![](../assets/schema3.png)

* Dichiarare un campo di identità per identificare l’oggetto dell’evento. Se non viene specificata alcuna identità, è possibile utilizzare una mappa di identità. Questo non è consigliato.

![](../assets/schema4.png)

* Se si desidera che questi dati siano disponibili per la ricerca successiva in un viaggio, contrassegnare lo schema e il dataset per il profilo.

![](../assets/schema5.png)

![](../assets/schema6.png)

* Potete includere campi di dati per acquisire qualsiasi altro dato contestuale da includere nell&#39;evento, ad esempio informazioni sull&#39;utente, sul dispositivo da cui è stato generato l&#39;evento, sulla posizione o su qualsiasi altra circostanza significativa correlata all&#39;evento.

![](../assets/schema7.png)

![](../assets/schema8.png)