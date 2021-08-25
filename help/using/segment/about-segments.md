---
product: adobe campaign
title: Informazioni sui segmenti Adobe Experience Platform
description: Scopri come configurare un segmento Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 0%

---

# Informazioni sui segmenti Adobe Experience Platform {#about-segments}

Se utilizzi il [Servizio di segmentazione di Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) per creare i segmenti, puoi sfruttarli in [!DNL Journey Orchestration]. Grazie a un’attività evento dedicata, puoi fare entrare o proseguire singoli utenti in un percorso in base alle entrate e alle uscite dei segmenti Adobe Experience Platform. Questo consente anche di creare condizioni complesse nei percorsi utilizzando l’editor di espressioni semplice o avanzato.

Supponiamo che tu abbia un segmento &quot;cliente argento&quot;. Con questa attività, puoi fare entrare tutti i nuovi clienti in argento in un percorso e inviare loro una serie di messaggi personalizzati. Puoi anche creare facilmente condizioni basate su questo segmento.

Di seguito sono elencate le possibilità offerte da [!DNL Journey Orchestration] con i segmenti:

* Accedi all’elenco dei segmenti di Adobe Experience Platform. Consulta [Creazione di un segmento](../segment/creating-a-segment.md).
* Crea segmenti direttamente in [!DNL Journey Orchestration] nello stesso modo in cui li crei utilizzando il servizio di segmentazione. Consulta [Creazione di un segmento](../segment/creating-a-segment.md).
* Sfrutta i segmenti nelle condizioni del tuo percorso utilizzando l’editor di espressioni semplice o avanzato. Consulta [Uso dei segmenti nelle condizioni](../segment/using-a-segment.md).
* Aggiungi un evento **[!UICONTROL Segment qualification]** al tuo percorso per ascoltare le entrate e le uscite dei profili nei segmenti Adobe Experience Platform. Consulta [Attività eventi](../building-journeys/segment-qualification-events.md).

## Metodo di valutazione in Journey Orchestration {#evaluation-method-in-journey-orchestration}

In Journey Orchestration, i tipi di pubblico vengono generati dalle definizioni dei segmenti utilizzando uno dei seguenti metodi di valutazione:

* Segmentazione in streaming : l’elenco del pubblico per il segmento viene mantenuto aggiornato in tempo reale, mentre i nuovi dati scorrono nel sistema.
* Segmentazione in batch: l’elenco del pubblico per il segmento viene aggiornato ogni ora, in base ai dati arrivati nell’ora precedente.

La determinazione tra segmentazione batch e segmentazione in streaming viene effettuata dal sistema per ogni definizione di segmento, in base alla complessità e al costo della valutazione della regola del segmento.

Puoi visualizzare il metodo di valutazione per ciascun segmento nella colonna **[!UICONTROL Evaluation method]** dell’elenco dei segmenti.

Dopo aver definito per la prima volta un segmento, i profili vengono aggiunti al pubblico quando si qualificano.

Il backfill del pubblico dai dati precedenti può richiedere fino a 24 ore. Dopo che il pubblico è stato riempito di nuovo, il pubblico viene costantemente aggiornato ed è sempre pronto per il targeting.