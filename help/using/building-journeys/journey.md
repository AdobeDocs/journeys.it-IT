---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sulla creazione di percorsi
description: In qualità di utente aziendale, scopri come combinare attività di evento, orchestrazione e azione per creare un percorso.
feature: Percorsi
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 15%

---


# Creazione di un percorso {#concept_gq5_sqt_52b}

Questo passaggio viene eseguito dall&#39; **utente aziendale**. Qui è dove si creano i percorsi. Combina le diverse attività relative a un evento, un percorso e un’azione in modo da creare scenari tra canali con più passaggi.

L’interfaccia di percorso ti consente di trascinare facilmente le attività dalla palette nell’area di lavoro. Puoi anche fare doppio clic su un’attività per aggiungerla nell’area di lavoro al passaggio successivo disponibile. Ogni attività ha un ruolo specifico e un ruolo specifico nel processo. Le attività vengono sequenziate. Al termine di un’attività, il flusso continua ed elabora l’attività successiva e così via.

È consentito un solo spazio dei nomi al percorso. Quando rilasci il primo evento, gli eventi con namespace diversi saranno disattivati. Se il primo evento non dispone di uno spazio dei nomi, tutti gli eventi con uno spazio dei nomi saranno disattivati. Consulta [questa pagina](../event/selecting-the-namespace.md). Inoltre, i gruppi di campi Adobe Experience Platform sono disattivati se il percorso dispone di eventi senza spazio dei nomi. Infine, se utilizzi più eventi nello stesso percorso, questi dovranno utilizzare lo stesso namespace.

Quando si avvia un nuovo percorso, gli elementi che non possono essere eliminati nell’area di lavoro come primo passaggio vengono nascosti. Questo riguarda tutte le azioni, l&#39;attività della condizione, l&#39;attesa e la reazione.

## Avvio rapido {#creating_journey}

Di seguito sono riportati i passaggi principali per creare e pubblicare un percorso.

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Home]**.

   Viene visualizzato l’elenco dei percorsi. Per ulteriori informazioni sull&#39;interfaccia, consulta [questa pagina](../building-journeys/using-the-journey-designer.md) .

   ![](../assets/journey30.png)

1. Fai clic su **[!UICONTROL Create]** per creare un nuovo percorso.

   ![](../assets/journey31.png)

1. Modifica le proprietà del percorso nel riquadro di configurazione visualizzato sul lato destro. Consulta [questa pagina](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Per iniziare, trascina e rilascia un’attività evento dalla palette nell’area di lavoro. Puoi anche fare doppio clic su un’attività per aggiungerla all’area di lavoro.

   ![](../assets/journey33.png)

1. Trascina e rilascia le altre attività e configurale. Consulta le pagine [Attività evento](../building-journeys/event-activities.md), [Informazioni sulle attività di orchestrazione](../building-journeys/about-orchestration-activities.md) e [Informazioni sulle attività di azione](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Il percorso viene salvato automaticamente. Verifica il percorso e pubblicalo. Consulta [test del percorso](../building-journeys/testing-the-journey.md) e [Pubblicazione del percorso](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Terminazione di un percorso {#ending_a_journey}

Ci sono due modi per terminare un percorso:

* La persona arriva all&#39;ultima attività di un percorso. Quest’ultima attività può essere un’attività finale o un’altra. Non vi è alcun obbligo di terminare un percorso con un’attività finale. Consulta [questa pagina](../building-journeys/end-activity.md).
* La persona arriva a un’attività condizione (o un’attività di attesa con una condizione) e non corrisponde a nessuna delle condizioni.

La persona può quindi rientrare nel percorso se è consentito il rientro. Consulta [questa pagina](../building-journeys/changing-properties.md).
