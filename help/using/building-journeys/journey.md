---
title: Informazioni sulla creazione di percorsi
description: Scopri come creare un percorso
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
source-git-commit: d5c013ed6031e8138a8e2c099fc28af82966d3ec

---



# Creazione di un percorso {#concept_gq5_sqt_52b}

Questo passaggio viene eseguito dall&#39;utente **** aziendale. Qui si creano i percorsi. Combinate le diverse attività di evento, orchestrazione e azione per creare scenari multicanale con più passaggi.

L’interfaccia di viaggio consente di trascinare e rilasciare facilmente le attività dalla palette al quadro. Potete anche fare doppio clic su un&#39;attività per aggiungerla nell&#39;area di lavoro al passaggio successivo disponibile. Ogni attività ha un ruolo specifico e si colloca nel processo. Le attività sono sequenziate. Al termine di un&#39;attività, il flusso continua ed elabora l&#39;attività successiva, e così via.

È consentito un solo spazio dei nomi per percorso. Quando si elimina il primo evento, gli eventi con spazi dei nomi diversi saranno disattivati. Se il primo evento non dispone di uno spazio nomi, tutti gli eventi con uno spazio dei nomi saranno disattivati. Vedere [](../event/selecting-the-namespace.md). Inoltre, i gruppi di campi di Experience Platform sono disabilitati se il viaggio include eventi senza uno spazio nomi. Infine, se si utilizzano diversi eventi nello stesso percorso, è necessario che utilizzino lo stesso spazio nomi.

## Quick start {#creating_journey}

Di seguito sono riportati i passaggi principali per creare e pubblicare un viaggio.

1. Nel menu principale, fate clic sulla **[!UICONTROL Home]** scheda.

   Viene visualizzato l’elenco dei viaggi. Consultate [](../building-journeys/using-the-journey-designer.md) per ulteriori informazioni sull&#39;interfaccia.

   ![](../assets/journey30.png)

1. Fai clic **[!UICONTROL Create]** per creare un nuovo percorso.

   ![](../assets/journey31.png)

1. Modifica le proprietà del viaggio nel riquadro di configurazione visualizzato sul lato destro. Vedere [](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Per iniziare, trascinate un&#39;attività dell&#39;evento dalla palette al quadro. Potete anche fare doppio clic su un&#39;attività per aggiungerla al quadro.

   ![](../assets/journey33.png)

1. Trascina e rilascia le altre attività e configurale. Vedi [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) e [](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Il viaggio viene salvato automaticamente. Verifica il percorso e pubblicalo. Vedere [](../building-journeys/testing-the-journey.md) e [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Fine di un viaggio {#ending_a_journey}

Esistono due modi per terminare un viaggio:

* La persona arriva all&#39;ultima attività di un percorso. Quest&#39;ultima attività può essere un&#39;attività finale o un&#39;altra. Non esiste alcun obbligo di terminare un percorso con un&#39;attività finale. Vedere [](../building-journeys/end-activity.md).
* La persona arriva a un&#39;attività di condizione (o un&#39;attività di attesa con una condizione) e non corrisponde ad alcuna delle condizioni.

La persona può quindi rientrare nel percorso se è consentito il rientro. Vedere [](../building-journeys/changing-properties.md).
