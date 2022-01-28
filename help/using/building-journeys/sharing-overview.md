---
product: adobe campaign
title: Panoramica sulla condivisione delle fasi del percorso
description: Panoramica sulla condivisione delle fasi del percorso
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 034473b318eddf93e4ed27d9cbe9e18dab1d96cb
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 3%

---

# Panoramica sulla condivisione delle fasi del percorso{#sharing-overview}

[!DNL Journey Orchestration] invia automaticamente i dati sulle prestazioni del percorso a Adobe Experience Platform in modo che possano essere combinati con altri dati a scopo di analisi.

>[!NOTE]
>
>Questa funzione è attivata per impostazione predefinita su tutte le istanze per gli eventi dei passaggi percorso. Per gli eventi delle fasi del profilo di percorso, l’attivazione avviene su richiesta. Non è possibile modificare o aggiornare gli schemi e i set di dati creati durante il provisioning per gli eventi delle fasi. Per impostazione predefinita, questi schemi e set di dati sono in modalità di sola lettura.

Ad esempio, hai impostato un percorso che invia più e-mail. Questa funzionalità consente di combinare [!DNL Journey Orchestration] dati con dati evento a valle come quante conversioni si sono verificate, quanto coinvolgimento è avvenuto sul sito web o quante transazioni sono avvenute nel negozio. Le informazioni sul percorso possono essere combinate con i dati sul Adobe Experience Platform, provenienti da altre proprietà digitali o da proprietà offline per fornire una visione più completa delle prestazioni.

[!DNL Journey Orchestration] crea automaticamente gli schemi e i flussi necessari nei set di dati in Adobe Experience Platform per ogni passaggio effettuato da un singolo utente in un percorso. Un evento step corrisponde a un singolo spostamento da un nodo all&#39;altro in un percorso. Ad esempio, in un percorso con un evento, una condizione e un’azione, vengono inviati tre eventi di passaggio a Adobe Experience Platform.

L’elenco dei campi XDM passati è completo. Alcuni contengono codici generati dal sistema e altri hanno nomi descrittivi leggibili dall&#39;uomo. Gli esempi includono l’etichetta dell’attività del percorso o lo stato del passaggio: quante volte un&#39;azione è scaduta o terminata con un errore.

>[!CAUTION]
>
>Impossibile attivare i set di dati per il servizio di profilo in tempo reale. Assicurati che la **[!UICONTROL Profile]** l&#39;interruttore è disattivato.

I percorsi inviano i dati mentre si verificano, in modo streaming. È possibile eseguire query su questi dati utilizzando il servizio query. È possibile connettersi a strumenti di Customer Journey Analytics o altri strumenti BI per visualizzare i dati relativi a questi passaggi.

Vengono creati i seguenti schemi:

* Schema evento del profilo del passaggio del percorso per [!DNL Journey Orchestration] - Eventi di esperienza per i passaggi effettuati in un Percorso insieme a una mappa di identità da utilizzare per la mappatura a un singolo partecipante a un Percorso.
* Schema evento del passaggio del percorso per [!DNL Journey Orchestration] - Evento Percorso associato a un Percorso di metadati.
* Schema percorso con campi Percorso per [!DNL Journey Orchestration] - Metadati Percorso per descrivere i Percorsi.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Vengono passati i seguenti set di dati:

* Schema evento del profilo del passaggio del percorso per [!DNL Journey Orchestration]
* Eventi percorso
* Percorsi

![](../assets/sharing3.png)

Gli elenchi dei campi XDM passati a Adobe Experience Platform sono descritti di seguito.

* [Elenco dei campi evento del passaggio](../building-journeys/sharing-field-list.md)
* [Campi evento del passaggio precedente](../building-journeys/sharing-legacy-fields.md)

Per ulteriori informazioni sugli eventi dei passaggi che trasmettono a Adobe Experience Platform, consulta questo articolo [video tutorial](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).

## Integrazione con Customer Percorsi Analytics{#integration-cja}

Gli eventi dei passaggi di Journey Orchestration possono essere collegati ad altri set di dati in [Customer Journey Analytics Adobe](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html). Il flusso di lavoro generale è il seguente:

* Il Customer Journey Analytics acquisisce il set di dati &quot;Evento passaggio Percorso&quot;.
* La **profileID** il campo nello &quot;schema evento del passaggio del Percorso per il Journey Orchestration&quot; associato è definito come campo Identity. Al Customer Journey Analytics, puoi collegare questo set di dati a qualsiasi altro set di dati con lo stesso valore dell’identificatore basato su persona.
* Se desideri utilizzare questo set di dati in Customer Journey Analytics, per l’analisi dei percorsi cross-channel, consulta questo [documentazione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html).
