---
title: Panoramica sulla condivisione delle fasi del percorso
description: Panoramica sulla condivisione delle fasi del percorso
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: c7a4d67af88827dfc852a281a7877efb2853facf
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 7%

---


# Panoramica sulla condivisione delle fasi del percorso{#sharing-overview}

[!DNL Journey Orchestration] invia automaticamente i dati sulle prestazioni del viaggio all&#39;Adobe Experience Platform, in modo che possa essere combinato con altri dati a scopo di analisi.

>[!NOTE]
>
>Questa funzione non è attivata per impostazione predefinita su tutte le istanze appena distribuite. L&#39;attivazione è su richiesta.

Ad esempio, hai impostato un percorso che invia più e-mail. Questa funzionalità consente di combinare [!DNL Journey Orchestration] i dati con i dati evento a valle, come il numero di conversioni verificatesi, l&#39;entità del coinvolgimento sul sito Web o il numero di transazioni avvenute nello store. Le informazioni sul viaggio possono essere combinate con dati sull&#39;Adobe Experience Platform, provenienti da altre proprietà digitali o da proprietà offline, per fornire una visione più completa delle prestazioni.

[!DNL Journey Orchestration] crea automaticamente gli schemi e i flussi necessari nei set di dati all&#39;Adobe Experience Platform per ogni passaggio effettuato da un utente in un determinato viaggio. Un evento step corrisponde a un singolo spostamento da un nodo all&#39;altro in un percorso. Ad esempio, in un percorso che include un evento, una condizione e un&#39;azione, vengono inviati all&#39;Adobe Experience Platform tre eventi step.

L&#39;elenco dei campi XDM che vengono passati è completo. Alcuni contengono codici generati dal sistema e altri hanno nomi comprensibili agli utenti. Alcuni esempi includono l’etichetta dell’attività di viaggio o lo stato del passaggio: quante volte un’azione è scaduta o terminata in un errore.

>[!CAUTION]
>
>Impossibile attivare i set di dati per il servizio di profilo in tempo reale. Assicurarsi che l&#39; **[!UICONTROL Profile]** interruttore sia disattivato.

I viaggi inviano i dati man mano che si verificano, in streaming. È possibile eseguire una query di questi dati utilizzando il servizio Query. È possibile connettersi a Customer Journey Analytics o ad altri strumenti BI per visualizzare i dati relativi a questi passaggi.

Vengono creati i seguenti schemi:

* Schema evento del profilo del passo del viaggio per [!DNL Journey Orchestration] - Eventi esperienza per i passaggi eseguiti in un viaggio insieme a una mappa identità da utilizzare per la mappatura a un singolo partecipante al viaggio.
* Schema evento passo viaggio per [!DNL Journey Orchestration] - evento passo viaggio associato a metadati viaggio.
* Schema di viaggio con campi di viaggio per [!DNL Journey Orchestration] - Metadati viaggio per descrivere i viaggi.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Vengono passati i seguenti set di dati:

* Schema evento profilo passo viaggio per [!DNL Journey Orchestration]
* Eventi passo viaggio
* Viaggi

![](../assets/sharing3.png)

Gli elenchi dei campi XDM passati all&#39;Adobe Experience Platform sono descritti di seguito:

* [Campi comuni degli eventi journeySteps](../building-journeys/sharing-common-fields.md)
* [Campi di esecuzione azione degli eventi journeyStep](../building-journeys/sharing-execution-fields.md)
* [Campi di recupero dati di journeyStep](../building-journeys/sharing-fetch-fields.md)
* [Campi di identità dell’evento di journeyStep](../building-journeys/sharing-identity-fields.md)
* [Campi del percorso](../building-journeys/sharing-journey-fields.md)

Per ulteriori informazioni sugli eventi dei passaggi da riportare ad Adobe Experience Platform, guardate questo video [di](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)esercitazione.
