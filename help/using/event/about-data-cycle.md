---
product: adobe campaign
solution: Journey Orchestration
title: Ciclo di dati evento
description: Scopri il ciclo dei dati dell’evento
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 78%

---


# Ciclo dei dati {#section_r1f_xqt_pgb}

Gli eventi sono chiamate API POST. Gli eventi vengono inviati ad Adobe Experience Platform tramite le API Streaming Ingestion. La destinazione URL degli eventi inviati tramite le API di messaggistica transazionale è denominata “entrata”. Il payload degli eventi segue la formattazione XDM.

Nell’intestazione del payload sono contenute le informazioni richieste per il funzionamento delle API Streaming Ingestion, oltre alle informazioni necessarie all’operatività di [!DNL Journey Orchestration], come l’ID evento e una parte del corpo del payload, e infine le informazioni da utilizzare nei percorsi (ad esempio, nel corpo, la quantità presente in un carrello abbandonato). Lo streaming ingestion può avvenire in modalità autenticata e non autenticata. Per informazioni dettagliate sulle API Streaming Ingestion, fai riferimento a [questo collegamento](https://docs.adobe.com/content/help/it-IT/experience-platform/xdm/api/getting-started.html).

Una volta arrivati attraverso le API Streaming Ingestion, gli eventi si propagano in un servizio interno denominato Pipeline e infine passano ad Adobe Experience Platform. Se nello schema dell’evento è abilitato il flag Profilo del cliente in tempo reale ed è presente un ID set di dati con il medesimo flag, tale schema si propaga nel Profilo del cliente in tempo reale.

Per gli eventi generati dal sistema, la pipeline filtra gli eventi che presentano un payload contenente [!DNL Journey Orchestration] eventIDs (vedi il processo di creazione dell’evento riportato di seguito) fornito da [!DNL Journey Orchestration] e contenuto nel payload dell’evento. Per gli eventi basati su regole, il sistema identifica l&#39;evento utilizzando la condizione eventID . [!DNL Journey Orchestration] fa da listener agli eventi, il che attiva il percorso corrispondente.
