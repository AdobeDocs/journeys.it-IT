---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sulla creazione di percorsi
description: In qualità di utente aziendale, scopri come combinare attività di evento, orchestrazione e azione per creare un percorso.
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 17%

---


# Creazione di un percorso {#concept_gq5_sqt_52b}

Questo passaggio viene eseguito dall&#39; **utente aziendale**. Qui si creano i percorsi. Combina le diverse attività relative a un evento, un percorso e un’azione in modo da creare scenari tra canali con più passaggi.

L&#39;interfaccia del percorso consente di trascinare e rilasciare facilmente le attività dalla palette al quadro. Potete anche fare doppio clic su un&#39;attività per aggiungerla nell&#39;area di lavoro al passaggio successivo disponibile. Ogni attività ha un ruolo specifico e si colloca nel processo. Le attività sono sequenziate. Al termine di un&#39;attività, il flusso continua ed elabora l&#39;attività successiva, e così via.

È consentito un solo spazio dei nomi per percorso. Quando si elimina il primo evento, gli eventi con spazi dei nomi diversi saranno disattivati. Se il primo evento non dispone di uno spazio nomi, tutti gli eventi con uno spazio dei nomi saranno disattivati. Consulta [questa pagina](../event/selecting-the-namespace.md). Inoltre, i gruppi di campi Adobe Experience Platform sono disabilitati se l&#39;percorso dispone di eventi senza uno spazio nomi. Infine, se si utilizzano diversi eventi nello stesso percorso, è necessario che utilizzino lo stesso spazio nomi.

## Avvio rapido {#creating_journey}

Di seguito sono riportati i passaggi principali per creare e pubblicare un percorso.

1. Nel menu principale, fai clic sulla scheda **[!UICONTROL Home]**.

   Viene visualizzato l’elenco degli percorsi. Fare riferimento a [questa pagina](../building-journeys/using-the-journey-designer.md) per ulteriori informazioni sull&#39;interfaccia.

   ![](../assets/journey30.png)

1. Fate clic su **[!UICONTROL Create]** per creare un nuovo percorso.

   ![](../assets/journey31.png)

1. Modifica le proprietà del percorso nel riquadro di configurazione visualizzato sul lato destro. Consulta [questa pagina](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Per iniziare, trascinate un&#39;attività dell&#39;evento dalla palette al quadro. Potete anche fare doppio clic su un&#39;attività per aggiungerla al quadro.

   ![](../assets/journey33.png)

1. Trascina e rilascia le altre attività e configurale. Fare riferimento alle pagine [Attività evento](../building-journeys/event-activities.md), [Informazioni sulle attività di orchestrazione](../building-journeys/about-orchestration-activities.md) e [Informazioni sulle attività di azione](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Il percorso viene salvato automaticamente. Verificate il percorso e pubblicatelo. Vedere [test del percorso](../building-journeys/testing-the-journey.md) e [Pubblicazione del percorso](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Fine di un percorso {#ending_a_journey}

Esistono due modi per terminare un percorso:

* La persona arriva all&#39;ultima attività di un percorso. Quest&#39;ultima attività può essere un&#39;attività finale o un&#39;altra. Non è previsto l&#39;obbligo di terminare un percorso con un&#39;attività finale. Consulta [questa pagina](../building-journeys/end-activity.md).
* La persona arriva a un&#39;attività di condizione (o un&#39;attività di attesa con una condizione) e non corrisponde ad alcuna delle condizioni.

La persona può quindi rientrare nel percorso se è consentito il rientro. Consulta [questa pagina](../building-journeys/changing-properties.md).
