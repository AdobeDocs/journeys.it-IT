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
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---


# Informazioni sulle attività eventi {#concept_rws_1rt_52b}

Gli eventi configurati dall&#39;utente tecnico (vedere [](../event/about-events.md)) vengono visualizzati nella prima categoria della palette, sul lato sinistro dello schermo.

![](../assets/journey43.png)

Iniziate sempre il viaggio trascinando e rilasciando un&#39;attività dell&#39;evento. Potete anche fare doppio clic su di esso.

![](../assets/journey44.png)

Quando fate clic sull&#39;attività dell&#39;evento nell&#39;area di lavoro, viene visualizzato il riquadro di configurazione dell&#39;attività. Per impostazione predefinita, quando si utilizza lo stesso evento più volte, al nome dell&#39;evento nell&#39;area di lavoro viene aggiunto un numero incrementale. Inoltre, potete utilizzare il **[!UICONTROL Label]** campo per aggiungere un suffisso al nome dell&#39;evento che verrà visualizzato sotto l&#39;attività nell&#39;area di lavoro. Questo è utile per identificare gli eventi nel quadro, soprattutto se si utilizza più volte lo stesso evento. Inoltre, faciliterà il debug in caso di errori e faciliterà la lettura dei report.

![](../assets/journey33.png)

## Utilizzo avanzato: eventi con attesa parallela{#section_vxv_h25_pgb}

**Come si può ascoltare un evento solo durante un certo periodo di tempo?**

Un&#39;attività dell&#39;evento posizionata nel percorso ascolta gli eventi in modo indefinito. Per ascoltare un evento solo durante un certo periodo di tempo, dovete aggiungere un&#39;attività di attesa parallela al percorso dell&#39;evento. Il viaggio quindi ascolterà l&#39;evento durante il tempo specificato nell&#39;attività di attesa. Se un evento viene ricevuto durante tale periodo, la persona scorre nel percorso dell&#39;evento. In caso contrario, il cliente si troverà nel percorso di attesa.

Ad esempio, hai inviato una prima notifica di benvenuto a un cliente e vuoi inviare una notifica push con sconto per il pasto solo se il cliente entra nel ristorante entro le prossime 6 ore. A questo scopo, creerete un secondo percorso (parallelo all&#39;evento ristorante uno) con un&#39;attività di attesa di 6 ore. Se l&#39;evento del ristorante viene ricevuto meno di 6 ore dopo il push di benvenuto, l&#39;attività push di sconto del pasto viene inviata. Se non viene ricevuto alcun evento ristorante entro le prossime 6 ore, la persona scorre attraverso il percorso di attesa.

![](../assets/journeyuc2_31.png)
