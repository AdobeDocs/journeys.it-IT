---
product: adobe campaign
title: Informazioni sulla creazione di percorsi
description: In qualità di utente aziendale, scopri come combinare attività di evento, orchestrazione e azione per creare un percorso.
feature: Journeys
role: User
level: Intermediate
exl-id: 540b5142-9323-4cc1-9b5a-3fa20a5945bf
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 13%

---

# Creazione di un percorso {#concept_gq5_sqt_52b}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home) per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


Questo passaggio viene eseguito dall&#39;**utente aziendale**. Qui è dove si creano i percorsi. Combina le diverse attività relative a eventi, orchestrazioni e azioni per creare scenari cross-channel con più passaggi.

L’interfaccia dei percorsi consente di trascinare facilmente le attività dalla palette all’area di lavoro. Puoi anche fare doppio clic su un’attività per aggiungerla nell’area di lavoro al passaggio successivo disponibile. Ogni attività ha un ruolo e un luogo specifici nel processo. Le attività sono in sequenza. Al termine di un’attività, il flusso continua ed elabora l’attività successiva e così via.

È consentito un solo spazio dei nomi per percorso. Quando rilasci il primo evento, gli eventi con spazi dei nomi diversi diventano grigi. Se il primo evento non ha uno spazio dei nomi, tutti gli eventi con uno spazio dei nomi saranno disattivati. Vedi [questa pagina](../event/selecting-the-namespace.md). Inoltre, i gruppi di campi di Adobe Experience Platform sono disattivati se il percorso ha eventi senza uno spazio dei nomi. E infine, se usi più eventi nello stesso percorso, devono usare lo stesso namespace.

Quando si avvia un nuovo percorso, gli elementi che non possono essere rilasciati nell’area di lavoro come primo passaggio vengono nascosti. Questo riguarda tutte le azioni, l’attività della condizione, l’attesa e la reazione.

## Guida rapida {#creating_journey}

Di seguito sono riportati i passaggi principali per creare e pubblicare un percorso.

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Home]**.

   Viene visualizzato l’elenco dei percorsi. Per ulteriori informazioni sull&#39;interfaccia, consultare [questa pagina](../building-journeys/using-the-journey-designer.md).

   ![](../assets/journey30.png)

1. Fare clic su **[!UICONTROL Create]** per creare un nuovo percorso.

   ![](../assets/journey31.png)

1. Modifica le proprietà del percorso nel riquadro di configurazione visualizzato sul lato destro. Consulta [questa pagina](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Per iniziare, trascina e rilascia nell’area di lavoro un’attività evento dalla palette. Puoi anche fare doppio clic su un’attività per aggiungerla all’area di lavoro.

   ![](../assets/journey33.png)

1. Trascina e rilascia le altre attività e configurale. Consulta le pagine [Attività evento](../building-journeys/event-activities.md), [Informazioni sulle attività di orchestrazione](../building-journeys/about-orchestration-activities.md) e [Informazioni sulle attività azione](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Il percorso viene salvato automaticamente. Verifica il percorso e pubblicalo. Vedi [verifica del percorso](../building-journeys/testing-the-journey.md) e [Pubblicazione del percorso](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Chiusura di un percorso {#ending_a_journey}

Un percorso può terminare per un singolo utente per due motivi:

* La persona arriva all’ultima attività di un percorso. Quest’ultima attività può essere un’attività finale o un’altra attività. Non c’è alcun obbligo di terminare un percorso con un’attività finale. Consulta [questa pagina](../building-journeys/end-activity.md).
* La persona arriva a un’attività condizione (o a un’attività attesa con una condizione) e non corrisponde a nessuna delle condizioni.

La persona può quindi rientrare nel percorso se il rientro è consentito. Consulta [questa pagina](../building-journeys/changing-properties.md).

Un percorso può essere chiuso per i motivi seguenti:

* Il percorso viene chiuso manualmente tramite il pulsante **[!UICONTROL Close to new entrances]**.
* È stata raggiunta la data di fine del percorso.

Quando un percorso viene chiuso (per uno dei motivi di cui sopra), avrà lo stato **[!UICONTROL Closed]**. Il percorso smetterà di far entrare nel percorso nuovi individui. Le persone già nel percorso finiranno normalmente il percorso. Dopo il timeout globale predefinito di 30 giorni, il percorso passerà allo stato **Completato**. Consulta questa [sezione](../building-journeys/changing-properties.md#entrance).

Nel caso in cui si debba fermare il progresso di tutti i singoli individui nel percorso, è possibile fermarlo. L’arresto del percorso causerà il timeout di tutti gli utenti del percorso.

Per informazioni su come chiudere o arrestare manualmente un percorso, fare riferimento a questa [sezione](../building-journeys/terminating-a-journey.md).
