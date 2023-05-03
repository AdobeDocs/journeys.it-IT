---
product: adobe campaign
title: Informazioni sulla creazione di percorsi
description: In qualità di utente aziendale, scopri come combinare attività di evento, orchestrazione e azione per creare un percorso.
feature: Journeys
role: User
level: Intermediate
exl-id: 540b5142-9323-4cc1-9b5a-3fa20a5945bf
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 21%

---

# Creazione di un percorso {#concept_gq5_sqt_52b}

Questo passaggio viene eseguito da **utente aziendale**. Qui è dove si creano i percorsi. Combina le diverse attività relative a un evento, un percorso e un’azione in modo da creare scenari tra canali con più passaggi.

L’interfaccia dei percorsi consente di trascinare facilmente le attività dalla palette all’area di lavoro. Puoi anche fare doppio clic su un’attività per aggiungerla all’area di lavoro in corrispondenza del prossimo passaggio disponibile. Ciascuna attività ha un ruolo specifico e un ruolo specifico nel processo. Le attività vengono sequenziate. Al termine di un’attività, il flusso continua ed elabora l’attività successiva e così via.

È consentito un solo spazio dei nomi al percorso. Quando rilasci il primo evento, gli eventi con namespace diversi saranno disattivati. Se il primo evento non dispone di uno spazio dei nomi, tutti gli eventi con uno spazio dei nomi saranno disattivati. Consulta [questa pagina](../event/selecting-the-namespace.md). Inoltre, i gruppi di campi Adobe Experience Platform sono disattivati se il percorso dispone di eventi senza spazio dei nomi. Infine, se utilizzi più eventi nello stesso percorso, questi dovranno utilizzare lo stesso namespace.

Quando si avvia un nuovo percorso, gli elementi che non possono essere eliminati nell’area di lavoro come primo passaggio vengono nascosti. Questo riguarda tutte le azioni, l’attività della condizione, l’attesa e la reazione.

## Guida introduttiva  {#creating_journey}

Di seguito sono riportati i passaggi principali per creare e pubblicare un percorso.

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Home]**.

   Viene visualizzato l’elenco dei percorsi. Fai riferimento a [questa pagina](../building-journeys/using-the-journey-designer.md) per ulteriori informazioni sull’interfaccia.

   ![](../assets/journey30.png)

1. Fai clic su **[!UICONTROL Create]** per creare un nuovo percorso.

   ![](../assets/journey31.png)

1. Modifica le proprietà del percorso nel riquadro di configurazione visualizzato sul lato destro. Consulta [questa pagina](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Per iniziare, trascina e rilascia un’attività evento dalla palette nell’area di lavoro. Puoi anche fare doppio clic su un’attività per aggiungerla all’area di lavoro.

   ![](../assets/journey33.png)

1. Trascina e rilascia le altre attività e configurale. Consulta le pagine [Attività evento](../building-journeys/event-activities.md), [Informazioni sulle attività di orchestrazione](../building-journeys/about-orchestration-activities.md) e [Informazioni sulle attività azione](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Il percorso viene salvato automaticamente. Verifica il percorso e pubblicalo. Vedi [verifica del percorso](../building-journeys/testing-the-journey.md) e [Pubblicazione del percorso](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Terminazione di un percorso {#ending_a_journey}

Un percorso può terminare per un individuo per due motivi:

* La persona arriva all&#39;ultima attività di un percorso. Quest’ultima attività può essere un’attività finale o un’altra. Non vi è alcun obbligo di terminare un percorso con un’attività finale. Consulta [questa pagina](../building-journeys/end-activity.md).
* La persona arriva a un’attività condizione (o un’attività di attesa con una condizione) e non corrisponde a nessuna delle condizioni.

La persona può quindi rientrare nel percorso se è consentito il rientro. Consulta [questa pagina](../building-journeys/changing-properties.md).

Un percorso può chiudersi per i motivi seguenti:

* Il percorso viene chiuso manualmente tramite il **[!UICONTROL Close to new entrances]** pulsante .
* La data di fine del percorso è raggiunta.

Quando un percorso viene chiuso (per uno qualsiasi dei motivi di cui sopra), avrà lo stato **[!UICONTROL Closed]**. Il percorso smetterà di lasciare entrare nuovi individui nel percorso. Le persone già nel percorso finiranno normalmente il percorso. Dopo il timeout globale predefinito di 30 giorni, il percorso passerà al **Completato** stato. Consulta questa [sezione](../building-journeys/changing-properties.md#entrance).

Nel caso tu debba interrompere il progresso di tutti gli individui nel percorso, puoi fermarlo. Arrestare il percorso causerà il timeout di tutti gli individui nel percorso.

Per informazioni su come chiudere o arrestare manualmente un percorso, consulta questo [sezione](../building-journeys/terminating-a-journey.md).
