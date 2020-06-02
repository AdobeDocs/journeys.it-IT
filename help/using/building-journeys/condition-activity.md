---
title: Attività condizione
description: Informazioni sulle attività relative alle condizioni
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
source-git-commit: 11c266b035bc1bb83cccf4e3958e54e1eb00e9f4
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 1%

---


# Attività condizione{#section_e2n_pft_dgb}

Sono disponibili quattro tipi di condizioni:

* [Condizione Origine dati](#data_source_condition)
* [Condizione di tempo](#time_condition)
* [Suddivisione percentuale](#percentage_split)
* [Data, condizione](#date_condition)

![](../assets/journey49.png)

## Informazioni sull&#39;attività Condizione {#about_condition}

Fare clic **[!UICONTROL Add a path]** per definire più condizioni. Per ogni condizione, dopo l&#39;attività viene aggiunto un nuovo percorso nel quadro.

![](../assets/journey47.png)

Si noti che la progettazione dei viaggi ha un impatto funzionale. Quando più percorsi sono definiti dopo una condizione, viene eseguito solo il primo percorso idoneo. Ciò significa che potete variare la priorità dei percorsi posizionandoli sopra o sotto l’uno dell’altro. Ad esempio, se la condizione del primo percorso è &quot;La persona è un VIP&quot; e la condizione del secondo percorso è &quot;La persona è un maschio&quot;. Se una persona che soddisfa entrambe le condizioni (un maschio che è un VIP) supera questo passaggio, il primo percorso sarà scelto anche se è anche idoneo al secondo, perché il primo percorso è &quot;sopra&quot;. Per modificare questa priorità, spostare le attività in un altro ordine verticale.

![](../assets/journey48.png)

Puoi creare un altro percorso per audience non idonee alle condizioni definite selezionando **[!UICONTROL Show path for other cases than the one(s) above]**. Questa opzione non è disponibile in condizioni divise. Vedere [Dividi](#percentage_split)percentuali.

La modalità semplice consente di eseguire semplici query basate su una combinazione di campi. Tutti i campi disponibili sono visualizzati sul lato sinistro dello schermo. Trascinare i campi nella zona principale. Per combinare i diversi elementi, collegateli tra loro per creare diversi gruppi e/o livelli di gruppo. È quindi possibile selezionare un operatore logico per combinare elementi sullo stesso livello:

* E: un&#39;intersezione di due criteri. Vengono presi in considerazione solo gli elementi che corrispondono a tutti i criteri.
* O: un&#39;unione di due criteri. Vengono presi in considerazione gli elementi che corrispondono ad almeno uno dei due criteri.

![](../assets/journey64.png)

Se utilizzi il servizio [di segmentazione della](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html) piattaforma per creare i tuoi segmenti, puoi sfruttarli nelle tue condizioni di viaggio. Fare riferimento a [Utilizzo dei segmenti nelle condizioni](../segment/using-a-segment.md).


>[!NOTE]
>
>Non è possibile eseguire query sulle serie temporali (ad esempio un elenco di acquisti, clic passati sui messaggi) con l&#39;editor semplice. A questo scopo dovrete utilizzare l&#39;editor avanzato. A questo proposito, consulta la sezione [](../expression/expressionadvanced.md).

## Condizione Origine dati {#data_source_condition}

Questo consente di definire una condizione in base ai campi delle origini dati o agli eventi precedentemente inseriti nel percorso. Per ulteriori informazioni sull&#39;utilizzo dell&#39;editor di espressioni, vedere [](../expression/expressionadvanced.md). Utilizzando l&#39;editor di espressioni avanzate, potete impostare condizioni più avanzate per manipolare le raccolte o utilizzare origini dati che richiedono il passaggio di parametri. A questo proposito, consulta la sezione [](../datasource/external-data-sources.md).

![](../assets/journey50.png)

## Condizione di tempo{#time_condition}

Questo consente di eseguire diverse azioni in base all’ora del giorno e/o del giorno della settimana. Ad esempio, potete decidere di inviare messaggi SMS durante il giorno e e-mail di notte nei giorni feriali.

>[!NOTE]
>
>Il fuso orario non è più specifico a una condizione e ora è definito a livello di percorso nelle proprietà del viaggio. A questo proposito, consulta la sezione [](../building-journeys/timezone-management.md).

![](../assets/journey51.png)

## Suddivisione percentuale {#percentage_split}

Questa opzione consente di dividere in modo casuale l&#39;audience per definire un&#39;azione diversa per ciascun gruppo. Definire il numero di divisioni e la partizione per ciascun percorso. Il calcolo della divisione è statistico in quanto il sistema non è in grado di prevedere quante persone scorreranno in questa attività del viaggio. Di conseguenza, la suddivisione presenta un margine di errore molto basso. Questa funzione è basata su un meccanismo casuale Java (vedere questa [pagina](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)).

>[!NOTE]
>
>Tenere presente che non è presente alcun pulsante per aggiungere un percorso nella condizione di suddivisione in percentuale. Il numero di percorsi dipende dal numero di divisioni. In condizioni divise, non è possibile aggiungere un percorso per altri casi, in quanto non può verificarsi. Le persone entreranno sempre in uno dei percorsi divisi.


![](../assets/journey52.png)

## Data, condizione {#date_condition}

Questo consente di definire un flusso diverso in base alla data. Ad esempio, se la persona immette il passaggio durante il periodo di &quot;vendita&quot;, gli invierai un messaggio specifico. Il resto dell&#39;anno, manderà un altro messaggio.

>[!NOTE]
>
>Il fuso orario non è più specifico a una condizione e ora è definito a livello di percorso nelle proprietà del viaggio. A questo proposito, consulta la sezione [](../building-journeys/timezone-management.md).

![](../assets/journey53.png)
