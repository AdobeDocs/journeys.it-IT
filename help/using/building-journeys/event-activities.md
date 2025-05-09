---
product: adobe campaign
title: Informazioni sulle attività eventi
description: Scopri le attività degli eventi
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 1%

---

# Informazioni sulle attività eventi {#concept_rws_1rt_52b}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


Gli eventi configurati dall&#39;utente tecnico (vedere [questa pagina](../event/about-events.md)) sono tutti visualizzati nella prima categoria della palette, sul lato sinistro dello schermo.

![](../assets/journey43.png)

Avvia sempre il percorso trascinando un’attività evento. Puoi anche fare doppio clic su di esso.

![](../assets/journey44.png)

Quando fai clic sull’attività evento nell’area di lavoro, viene visualizzato il riquadro di configurazione dell’attività. Per impostazione predefinita, quando utilizzi lo stesso evento più volte, nell’area di lavoro viene aggiunto un numero incrementato al nome dell’evento. È inoltre possibile utilizzare il campo **[!UICONTROL Label]** per aggiungere un suffisso al nome dell&#39;evento che verrà visualizzato nell&#39;area di lavoro sotto l&#39;attività. Questo è utile per identificare gli eventi nell’area di lavoro, soprattutto se utilizzi lo stesso evento più volte. Semplifica inoltre il debug in caso di errori e semplifica la lettura dei rapporti.

![](../assets/journey33.png)

## Ascolto degli eventi durante uno specifico {#listening}

Un’attività evento posizionata nel percorso ascolta gli eventi a tempo indefinito. Per ascoltare un evento solo durante un determinato periodo di tempo, è necessario configurare un timeout per l’evento.

Il percorso ascolterà quindi l’evento durante il tempo specificato nel timeout. Se un evento viene ricevuto durante tale periodo, la persona scorrerà nel percorso dell’evento. In caso contrario, il cliente passa al percorso di timeout, se definito, oppure continua quel percorso. Se non è definito alcun percorso di timeout, l’impostazione di timeout fungerà da attività di attesa, facendo aspettare il profilo per un periodo di tempo che potrebbe essere interrotto se un evento si verifica prima della fine di tale attesa. Se desideri escludere i profili da tale percorso dopo il timeout, devi impostare un percorso di timeout.

Per configurare un timeout per un evento, effettua le seguenti operazioni:

1. Attiva l&#39;opzione **[!UICONTROL Enable the event timeout]** dalle proprietà evento.

1. Specifica il tempo di attesa dell&#39;evento da parte del percorso.

1. Se desideri inviare i singoli utenti a un percorso di timeout quando non viene ricevuto alcun evento entro il timeout specificato, abilita l&#39;opzione **[!UICONTROL Set the timeout path]**. Se questa opzione non è abilitata, il percorso continuerà per la singola persona una volta raggiunto il timeout.

   ![](../assets/event-timeout.png)

In questo esempio, il percorso invia un messaggio push di benvenuto a un cliente. Invia quindi un messaggio push con uno sconto sui pasti solo se il cliente entra nel ristorante entro il giorno successivo. Abbiamo quindi configurato l’evento del ristorante con un timeout di 1 giorno:

* Se l’evento del ristorante viene ricevuto meno di 1 giorno dopo il messaggio push di benvenuto, l’attività push per lo sconto sui pasti viene inviata.
* Se non viene ricevuto alcun evento del ristorante nel giorno successivo, la persona scorre attraverso il percorso di timeout.

Se si desidera configurare un timeout per più eventi posizionati dopo un&#39;attività **[!UICONTROL Wait]**, è necessario configurare il timeout solo per uno di questi eventi.

Il timeout verrà applicato a tutti gli eventi posizionati dopo l&#39;attività **[!UICONTROL Wait]**. Se non viene ricevuto alcun evento prima del timeout specificato, i singoli utenti scorrono in un singolo percorso di timeout o continuano tale percorso attraverso il ramo che esce dall’attività in cui sono state definite tali impostazioni di timeout.

![](../assets/event-timeout-group.png)
