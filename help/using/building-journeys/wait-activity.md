---
product: adobe campaign
title: Attività Attendi
description: Scopri l’attività Attendi
feature: Journeys
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 77fcc4ba02a855d4d584627625a08abb4af0da2f
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 7%

---

# Attività Attendi{#section_rlm_nft_dgb}

Se si desidera attendere prima di eseguire l&#39;attività successiva nel percorso, è possibile utilizzare un&#39;attività **[!UICONTROL Wait]**. Consente di stabilire il momento in cui verrà eseguita l’attività successiva. Sono disponibili tre opzioni:

* [Durata](#duration)
* [Personalizzato](#custom)
  <!--* [Email send time optimization](#email_send_time_optimization)-->

## Informazioni sull’attività Attendi{#about_wait}

Di seguito viene illustrato come assegnare la priorità alle attese quando si utilizzano più attese in parallelo. Se hanno la stessa configurazione temporale e una condizione diversa ma sovrapposta, l’attesa posizionata sopra avrà la priorità. Ad esempio, la condizione della prima attesa è &quot;essere donna&quot; e la condizione della seconda attesa in parallelo è &quot;essere VIP&quot;. Alla prima attività di attesa verrà assegnata la priorità.

Inoltre, se due diverse attese sono in parallelo, quella che si verifica per prima avrà la priorità, indipendentemente dalla sua posizione verticale. Ad esempio, se un’attesa di 1 ora è superiore e un’attesa di 30 minuti è inferiore, dopo 30 minuti verrà elaborata l’attesa di 30 minuti.

>[!NOTE]
>
>La durata massima di attesa è di 30 giorni.
>
>In modalità di test, il parametro **[!UICONTROL Wait time in test]** consente di definire la durata di ogni attività di attesa. Il tempo predefinito è di 10 secondi. In questo modo potrai ottenere rapidamente i risultati del test. Vedi [questa pagina](../building-journeys/testing-the-journey.md)

## Attesa durata{#duration}

Seleziona la durata dell’attesa prima dell’esecuzione dell’attività successiva.

![](../assets/journey55.png)

## Attesa personalizzata{#custom}

Questa opzione consente di definire una data personalizzata, ad esempio 12 luglio 2020 alle 17:00, utilizzando un’espressione avanzata basata su un campo proveniente da un evento o un’origine dati. Non consente di definire una durata personalizzata, ad esempio 7 giorni. L’espressione nell’editor espressioni deve fornire un formato dateTimeOnly. Vedi [questa pagina](../expression/expressionadvanced.md). Per ulteriori informazioni sul formato dateTimeOnly, vedere [questa pagina](../expression/data-types.md).

>[!NOTE]
>
>È possibile sfruttare un&#39;espressione dateTimeOnly o utilizzare una funzione per convertire in dateTimeOnly. Ad esempio: toDateTimeOnly(@{Event.offerOpened.activity.endTime}), il campo nell’evento è nel formato 2016-08-12T09:46:06Z.
>
>Il **fuso orario** è previsto nelle proprietà del percorso. Di conseguenza, oggi non è possibile dall’interfaccia puntare direttamente a un timestamp completo ISO-8601 che mescola tempo e scostamento fuso orario come 2016-08-12T09:46:06.982-05. Consulta [questa pagina](../building-journeys/timezone-management.md).

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
