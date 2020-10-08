---
title: Informazioni sulla creazione di percorsi
description: In qualità di utente aziendale, scopri come combinare attività di evento, orchestrazione e azione per creare un percorso.
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 13%

---



# Creazione di un percorso {#concept_gq5_sqt_52b}

This step is performed by the **business user**. Qui si creano i percorsi. Combina le diverse attività relative a un evento, un percorso e un’azione in modo da creare scenari tra canali con più passaggi.

L’interfaccia di viaggio consente di trascinare e rilasciare facilmente le attività dalla palette al quadro. Potete anche fare doppio clic su un&#39;attività per aggiungerla nell&#39;area di lavoro al passaggio successivo disponibile. Ogni attività ha un ruolo specifico e si colloca nel processo. Le attività sono sequenziate. Al termine di un&#39;attività, il flusso continua ed elabora l&#39;attività successiva, e così via.

Per ogni percorso è consentito un solo spazio dei nomi. Quando si elimina il primo evento, gli eventi con spazi dei nomi diversi saranno disattivati. Se il primo evento non dispone di uno spazio nomi, tutti gli eventi con uno spazio dei nomi saranno disattivati. A questo proposito, consulta la sezione [](../event/selecting-the-namespace.md). Inoltre, i gruppi di campi Adobe Experience Platform sono disabilitati se il viaggio include eventi senza uno spazio nomi. Infine, se si utilizzano diversi eventi nello stesso percorso, è necessario che utilizzino lo stesso spazio nomi.

## Quick start {#creating_journey}

Di seguito sono riportati i passaggi principali per creare e pubblicare un viaggio.

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Home]**.

   Viene visualizzato l’elenco dei viaggi. Per ulteriori informazioni sull’interfaccia, consulta la sezione [](../building-journeys/using-the-journey-designer.md).

   ![](../assets/journey30.png)

1. Click **[!UICONTROL Create]** to create a new journey.

   ![](../assets/journey31.png)

1. Modifica le proprietà del percorso nel riquadro di configurazione visualizzato sul lato destro. A questo proposito, consulta la sezione [](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Per iniziare, trascinate un&#39;attività dell&#39;evento dalla palette al quadro. Potete anche fare doppio clic su un&#39;attività per aggiungerla al quadro.

   ![](../assets/journey33.png)

1. Trascina e rilascia le altre attività e configurale. Vedi [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) e [](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Il viaggio viene salvato automaticamente. Verifica il percorso e pubblicalo. Vedere [](../building-journeys/testing-the-journey.md) e [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Fine di un viaggio {#ending_a_journey}

Esistono due modi per terminare un viaggio:

* La persona arriva all&#39;ultima attività di un percorso. Quest&#39;ultima attività può essere un&#39;attività finale o un&#39;altra. Non è previsto l&#39;obbligo di terminare un percorso con un&#39;attività finale. A questo proposito, consulta la sezione [](../building-journeys/end-activity.md).
* La persona arriva a un&#39;attività di condizione (o un&#39;attività di attesa con una condizione) e non corrisponde ad alcuna delle condizioni.

La persona può quindi rientrare nel percorso se è consentito il rientro. A questo proposito, consulta la sezione [](../building-journeys/changing-properties.md).
