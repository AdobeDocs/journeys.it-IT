---
product: adobe campaign
solution: Journey Orchestration
title: Attività attendi
description: Ulteriori informazioni sull'attività di attesa
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 4%

---


# Attività attendi{#section_rlm_nft_dgb}

Se desiderate aspettare prima di eseguire l&#39;attività successiva nel percorso, potete utilizzare un&#39; **[!UICONTROL Wait]** attività. Consente di definire il momento in cui verrà eseguita l&#39;attività successiva. Sono disponibili quattro opzioni:

* [Durata](#duration)
* [Data fissa](#fixed_date)
* [Personalizzato](#custom)

<!--* [Email send time optimization](#email_send_time_optimization)-->

## Informazioni sull&#39;attività Wait{#about_wait}

Di seguito viene illustrata la priorità delle attese quando si utilizzano più attese in parallelo. Se hanno la stessa configurazione di tempo e una condizione diversa ma sovrapposta, l&#39;attesa posizionata sopra sarà quella con priorità. Ad esempio, la condizione della prima attesa è &quot;essere una donna&quot; e la condizione della seconda attesa in parallelo è &quot;essere una VIP&quot;. La priorità della prima attività di attesa

Inoltre, se due diverse attese sono in parallelo, quella che si verifica per prima verrà definita come priorità, indipendentemente dalla posizione verticale. Ad esempio, se un’attesa di 1 ora è superiore e un’attesa di 30 minuti è inferiore, dopo 30 minuti verrà elaborata l’attesa di 30 minuti.

È possibile definire una condizione se si desidera limitare l&#39;attesa a una determinata popolazione.

>[!NOTE]
>
>La durata massima di attesa è di 30 giorni.
>
>In modalità di prova, il **[!UICONTROL Wait time in test]** parametro consente di definire l&#39;ora in cui ciascuna attività di attesa durerà. Il tempo predefinito è di 10 secondi. In questo modo sarà possibile ottenere rapidamente i risultati del test. Consulta [questa pagina](../building-journeys/testing-the-journey.md)

## Durata{#duration}

Selezionate la durata dell&#39;attesa prima dell&#39;esecuzione dell&#39;attività successiva.

![](../assets/journey55.png)

## Attesa data fissa{#fixed_date}

Selezionare la data per l&#39;esecuzione dell&#39;attività successiva.

![](../assets/journey56.png)

## Attesa personalizzata{#custom}

Questa opzione consente di definire una data personalizzata, ad esempio 12 luglio 2020 alle 17:00, utilizzando un&#39;espressione avanzata basata su un campo proveniente da un evento o da un&#39;origine dati. Non consente di definire una durata personalizzata, ad esempio 7 giorni. L&#39;espressione nell&#39;editor di espressioni deve fornire un formato dateTimeOnly. Consulta [questa pagina](../expression/expressionadvanced.md). Per ulteriori informazioni sul formato dateTimeOnly, consultate [questa pagina](../expression/data-types.md).

>[!NOTE]
>
>È possibile utilizzare un&#39;espressione dateTimeOnly o una funzione per convertire in dateTimeOnly. Ad esempio: ```toDateTimeOnly(@{Event.offerOpened.activity.endTime})```, il campo nel caso in cui si tratti del modulo 2016-08-12T09:46:06Z.
>
>Il fuso **** orario è previsto nelle proprietà del viaggio. Di conseguenza, oggi non è possibile dall&#39;interfaccia puntare direttamente a un tempo di mixaggio e un fuso orario ISO-8601 completo come 2016-08-12T09:46:06.982-05. Consulta [questa pagina](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you’ll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](../assets/journey57bis.png)-->
