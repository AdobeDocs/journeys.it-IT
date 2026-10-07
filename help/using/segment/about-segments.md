---
product: adobe campaign
title: Informazioni sui segmenti di Adobe Experience Platform
description: Scopri come configurare un segmento di Adobe Experience Platform
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
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
source-wordcount: '421'
ht-degree: 21%
---
# Informazioni sui segmenti di Adobe Experience Platform {#about-segments}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._


Se utilizzi il [Servizio di segmentazione di Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=it) per creare i tuoi segmenti, puoi sfruttarli in [!DNL Journey Orchestration]. Grazie a un’attività evento dedicata, puoi fare in modo che singoli utenti entrino o avanzino in un percorso basato sulle entrate e sulle uscite dei segmenti Adobe Experience Platform. Questo consente anche di creare condizioni complesse nei percorsi utilizzando l’editor di espressioni semplice o avanzato.

Supponiamo che tu abbia un segmento &quot;cliente silver&quot;. Con questa attività, puoi fare in modo che tutti i nuovi clienti silver entrino in un percorso e inviino loro una serie di messaggi personalizzati. Puoi anche creare facilmente le condizioni in base a questo segmento.

Di seguito sono riportate le possibilità offerte da [!DNL Journey Orchestration] con i segmenti:

* Accedi all’elenco dei segmenti di Adobe Experience Platform. Vedi [Creazione di un segmento](../segment/creating-a-segment.md).
* Creare i segmenti direttamente in [!DNL Journey Orchestration] nello stesso modo in cui li si crea utilizzando il servizio di segmentazione. Vedi [Creazione di un segmento](../segment/creating-a-segment.md).
* Sfrutta i segmenti nelle condizioni del percorso utilizzando l’editor di espressioni semplice o avanzato. Vedi [Utilizzo di segmenti nelle condizioni](../segment/using-a-segment.md).
* Aggiungi un evento **[!UICONTROL Segment qualification]** al percorso per ascoltare le entrate e le uscite dei profili nei segmenti Adobe Experience Platform. Vedi [Attività eventi](../building-journeys/segment-qualification-events.md).

## Metodo di valutazione in Journey Orchestration {#evaluation-method-in-journey-orchestration}

In Journey Orchestration, i tipi di pubblico vengono generati dalle definizioni dei segmenti utilizzando uno dei seguenti metodi di valutazione:

* Segmentazione in streaming: l’elenco dei tipi di pubblico per il segmento viene tenuto aggiornato in tempo reale durante il flusso dei nuovi dati nel sistema.
* Segmentazione in batch: l’elenco dei tipi di pubblico per il segmento viene aggiornato su base oraria, in base ai dati arrivati nell’ultima ora.

La determinazione tra segmentazione batch e segmentazione in streaming viene effettuata dal sistema per ogni definizione di segmento, in base alla complessità e al costo della valutazione della regola del segmento.

È possibile visualizzare il metodo di valutazione per ogni segmento nella colonna **[!UICONTROL Evaluation method]** dell&#39;elenco dei segmenti.

Dopo aver definito per la prima volta un segmento, i profili vengono aggiunti al pubblico quando sono idonei.

Il recupero del pubblico dai dati precedenti può richiedere fino a 24 ore. Dopo il recupero, il pubblico viene aggionato costantemente ed è sempre pronto per il targeting.