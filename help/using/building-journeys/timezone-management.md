---
title: Gestione del fuso orario
description: Informazioni sulla gestione del fuso orario
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
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# Gestione del fuso orario {#timezone_management}

La definizione del fuso orario è disponibile nelle seguenti attività:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Se l&#39;evento di ingresso del viaggio ha uno spazio dei nomi, il che significa che il viaggio può raggiungere il servizio di profilo cliente in tempo reale della piattaforma dati, il fuso orario è predefinito con quello specificato nel profilo del singolo che scorre nel viaggio. Se il profilo del singolo non contiene un fuso orario, viene utilizzato il fuso orario dell&#39;istanza. Potete contattare l’amministratore per conoscere il fuso orario dell’istanza.

![](../assets/journey73.png)

È inoltre possibile fissare il fuso orario. Deselezionare il fuso orario predefinito e selezionarne uno dall&#39;elenco a discesa. Se utilizzate un fuso orario fisso, sarà lo stesso per tutti gli utenti che accedono al viaggio.

![](../assets/journey72.png)

Infine, il fuso orario può essere dinamico per ogni persona che accede al passaggio. In questo caso, si utilizzerà l&#39;editor di espressioni per selezionare la posizione in cui si desidera che il sistema ottenga queste informazioni (può provenire da un evento o da un&#39;origine dati). Vedere [](../expression/expressionadvanced.md).


Le date di inizio e fine di un viaggio non possono essere collegate a un fuso orario specifico. Vengono automaticamente associati al fuso orario dell&#39;istanza.
