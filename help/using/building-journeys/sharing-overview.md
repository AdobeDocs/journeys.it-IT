---
title: Panoramica sulla condivisione delle fasi del viaggio
description: Panoramica sulla condivisione delle fasi del viaggio
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
source-git-commit: 26246bd44407a818afba8b80513cb62da9cf6ebd
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---


# Panoramica sulla condivisione delle fasi del viaggio{#sharing-overview}

Mediante l&#39;orchestrazione del percorso vengono inviati automaticamente i dati sulle prestazioni del viaggio ad Adobe Experience Platform, in modo che possano essere combinati con altri dati a scopo di analisi.

Ad esempio, hai impostato un percorso che invia più e-mail. Questa funzionalità consente di combinare i dati di orchestrazione del percorso con i dati evento a valle, come il numero di conversioni verificatesi, l&#39;entità del coinvolgimento sul sito Web o il numero di transazioni verificatesi nello store. Le informazioni sul viaggio possono essere combinate con dati sulla piattaforma, provenienti da altre proprietà digitali o da proprietà offline per fornire una visione più completa delle prestazioni.

L&#39;Orchestrazione del percorso crea automaticamente gli schemi e i flussi necessari nei set di dati della piattaforma per ogni passaggio eseguito da un individuo in un viaggio. Un evento step corrisponde a un singolo spostamento da un nodo all&#39;altro in un percorso. Ad esempio, in un viaggio che include un evento, una condizione e un&#39;azione, vengono inviati tre eventi step alla piattaforma.

L&#39;elenco dei campi XDM che vengono passati è completo. Alcuni contengono codici generati dal sistema e altri hanno nomi comprensibili agli utenti. Alcuni esempi includono l’etichetta dell’attività di viaggio o lo stato del passaggio: quante volte un&#39;azione è scaduta o terminata in un errore.

>[!CAUTION]
>
>Per impostazione predefinita, i set di dati non sono attivati per il servizio di profilo in tempo reale. Se desiderate un set di dati nel servizio profilo, dovete attivarlo (**Profile** toggle). Tenete presente che un elevato volume di eventi occuperà spazio di archiviazione nella quota. Procedere con attenzione prima di attivare un dataset per i profili
>
>![](../assets/sharing4.png)

I viaggi inviano i dati man mano che si verificano, in streaming. È possibile eseguire una query di questi dati utilizzando il servizio Query. Puoi connetterti ad Analytics del percorso cliente o ad altri strumenti BI per visualizzare i dati relativi a questi passaggi.

Vengono creati i seguenti schemi:

* Schema evento del profilo del passo del viaggio per l&#39;orchestrazione del viaggio - Eventi esperienza per i passaggi eseguiti in un viaggio insieme a una mappa identità da utilizzare per la mappatura a un singolo partecipante del viaggio.
* Schema evento del passo del viaggio per l&#39;orchestrazione del viaggio - evento del passo del viaggio associato a metadati del viaggio.
* Schema di viaggio con i campi di viaggio per l&#39;orchestrazione del viaggio - Metadati viaggio per descrivere i viaggi.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Vengono passati i seguenti set di dati:

* Schema evento del profilo del passo viaggio per l&#39;orchestrazione del viaggio
* Eventi passo viaggio
* Viaggi

![](../assets/sharing3.png)

Gli elenchi dei campi XDM passati alla piattaforma sono descritti di seguito:

* [Evento pathSteps campi comuni](../building-journeys/sharing-common-fields.md)
* [eventi pathStep campi di esecuzione azione](../building-journeys/sharing-execution-fields.md)
* [percorso:eventi, campi di recupero dati](../building-journeys/sharing-fetch-fields.md)
* [pathStep, campi di identità dell&#39;evento](../building-journeys/sharing-identity-fields.md)
* [campi di viaggio](../building-journeys/sharing-journey-fields.md)
