---
product: adobe campaign
title: Ciclo dati evento
description: Scopri il ciclo dei dati dell’evento
feature: Journeys
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
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
source-wordcount: '232'
ht-degree: 79%
---
# Ciclo dei dati {#section_r1f_xqt_pgb}

Gli eventi sono chiamate API POST. Gli eventi vengono inviati ad Adobe Experience Platform tramite le API per l’acquisizione in streaming. La destinazione URL degli eventi inviati tramite le API di messaggistica transazionale è denominata “inlet”. Il payload degli eventi segue la formattazione XDM.

Nell’intestazione del payload sono contenute le informazioni richieste per il funzionamento delle API per l’acquisizione in streaming, oltre alle informazioni necessarie all’operatività di [!DNL Journey Orchestration], come l’ID evento e una parte del corpo del payload, e infine le informazioni da utilizzare nei percorsi (ad esempio, nel corpo, la quantità presente in un carrello abbandonato). L’acquisizione in streaming può avvenire in modalità autenticata e non autenticata. Per informazioni dettagliate sulle API per l’acquisizione in streaming, fai riferimento a [questo collegamento](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=it).

Una volta arrivati attraverso le API per l’acquisizione in streaming, gli eventi si propagano in un servizio interno denominato Pipeline e infine passano ad Adobe Experience Platform. Se nello schema dell’evento è abilitato il flag Profilo del cliente in tempo reale ed è presente un ID set di dati con il medesimo flag, tale schema si propaga nel Profilo del cliente in tempo reale.

Per gli eventi generati dal sistema, la pipeline filtra gli eventi che presentano un payload contenente [!DNL Journey Orchestration] eventID (vedi il processo di creazione degli eventi illustrato di seguito) forniti da [!DNL Journey Orchestration] e contenuti nel payload degli eventi. Per gli eventi basati su regole, il sistema identifica l’evento utilizzando la condizione eventID. [!DNL Journey Orchestration] fa da listener agli eventi, il che attiva il percorso corrispondente.
