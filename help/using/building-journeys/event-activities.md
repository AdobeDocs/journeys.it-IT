---
title: Informazioni sulle attività eventi
description: Informazioni sulle attività degli eventi
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---


# Informazioni sulle attività eventi {#concept_rws_1rt_52b}

Gli eventi configurati dall&#39;utente tecnico (vedere [questa pagina](../event/about-events.md)) vengono visualizzati nella prima categoria della palette, sul lato sinistro dello schermo.

![](../assets/journey43.png)

Iniziate sempre il viaggio trascinando e rilasciando un&#39;attività dell&#39;evento. Potete anche fare doppio clic su di esso.

![](../assets/journey44.png)

Quando fate clic sull&#39;attività dell&#39;evento nell&#39;area di lavoro, viene visualizzato il riquadro di configurazione dell&#39;attività. Per impostazione predefinita, quando si utilizza lo stesso evento più volte, al nome dell&#39;evento nell&#39;area di lavoro viene aggiunto un numero incrementale. Inoltre, potete utilizzare il **[!UICONTROL Label]** campo per aggiungere un suffisso al nome dell&#39;evento che verrà visualizzato sotto l&#39;attività nell&#39;area di lavoro. Questo è utile per identificare gli eventi nel quadro, soprattutto se si utilizza più volte lo stesso evento. Inoltre, faciliterà il debug in caso di errori e faciliterà la lettura dei report.

![](../assets/journey33.png)

## Ascolto degli eventi durante un periodo di tempo specifico

Un&#39;attività dell&#39;evento posizionata nel percorso ascolta gli eventi in modo indefinito. Per ascoltare un evento solo durante un certo periodo di tempo, dovete configurare un timeout per l&#39;evento.

Il viaggio quindi ascolterà l&#39;evento durante il tempo specificato nel timeout. Se un evento viene ricevuto durante tale periodo, la persona scorre nel percorso dell&#39;evento. In caso contrario, il cliente percorrerà un percorso di timeout o terminerà il viaggio.

Per configurare un timeout per un evento, attenetevi alla procedura seguente:

1. Attivate l&#39; **[!UICONTROL Enable the event timeout]** opzione dalle proprietà dell&#39;evento.

1. Specificate il tempo di attesa del viaggio per l’evento.

1. Se desiderate inviare gli utenti a un percorso di timeout quando nessun evento viene ricevuto entro il timeout specificato, abilitate l&#39; **[!UICONTROL Set the timeout path]** opzione. Se questa opzione non è abilitata, il percorso terminerà per l&#39;individuo una volta raggiunto il timeout.

   ![](../assets/event-timeout.png)

In questo esempio, il viaggio invia una prima notifica di benvenuto a un cliente. Invia quindi un push con sconto per il pasto solo se il cliente entra nel ristorante entro il giorno successivo. Abbiamo pertanto configurato l&#39;evento ristorante con un timeout di 1 giorno:

* Se l&#39;evento del ristorante viene ricevuto meno di 1 giorno dopo il push di benvenuto, l&#39;attività push con sconto pasto viene inviata.
* Se non viene ricevuto alcun evento ristorante entro il giorno successivo, la persona scorre attraverso il percorso di timeout.

Se desiderate configurare un timeout per più eventi posizionati dopo un&#39; **[!UICONTROL Wait]** attività, dovete configurare il timeout solo per uno di questi eventi.

Il timeout verrà applicato a tutti gli eventi posizionati dopo l&#39; **[!UICONTROL Wait]** attività. Se non viene ricevuto alcun evento dopo il timeout specificato, gli utenti accederanno a un singolo percorso di timeout o termineranno il viaggio.

![](../assets/event-timeout-group.png)
