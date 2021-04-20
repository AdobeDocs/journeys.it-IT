---
product: adobe campaign
solution: Journey Orchestration
title: Attività condizione
description: Informazioni sulle attività di condizione
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 10%

---


# Attività condizione{#section_e2n_pft_dgb}

Sono disponibili quattro tipi di condizioni:

* [Condizione Origine dati](#data_source_condition)
* [Condizione di tempo](#time_condition)
* [Divisione percentuale](#percentage_split)
* [Condizione data](#date_condition)

![](../assets/journey49.png)

## Informazioni sull’attività Condizione {#about_condition}

Quando utilizzi più condizioni in un percorso, puoi definire etichette per ognuna di esse per identificarle più facilmente.

Fai clic su **[!UICONTROL Add a path]** per definire più condizioni. Per ogni condizione, dopo l’attività viene aggiunto un nuovo percorso nell’area di lavoro.

![](../assets/journey47.png)

La progettazione dei percorsi ha effetti funzionali. Quando più percorsi sono definiti dopo una condizione, viene eseguito solo il primo percorso idoneo. Significa che puoi variare la definizione delle priorità dei percorsi posizionandoli uno sopra l’altro o sotto l’altro.

Prendiamo ad esempio la condizione di un primo percorso &quot;La persona è un VIP&quot; e la condizione di un secondo percorso &quot;La persona è un maschio&quot;. Se una persona che soddisfa entrambe le condizioni (un maschio che è un VIP) supera questo passo, il primo percorso sarà scelto anche se è anche idoneo al secondo, perché il primo percorso è &quot;sopra&quot;. Per modificare questa priorità, sposta le attività in un altro ordine verticale.

![](../assets/journey48.png)

Puoi creare un altro percorso per tipi di pubblico non idonei alle condizioni definite selezionando **[!UICONTROL Show path for other cases than the one(s) above]**. Questa opzione non è disponibile in condizioni di suddivisione. Vedere [Percentuale di suddivisione](#percentage_split).

La modalità semplice consente di eseguire query semplici basate su una combinazione di campi. Tutti i campi disponibili vengono visualizzati sul lato sinistro dello schermo. Trascina i campi nella zona principale. Per combinare i diversi elementi, collegali tra loro per creare diversi gruppi e/o livelli di gruppo. Puoi quindi selezionare un operatore logico per combinare elementi sullo stesso livello:

* E: un’intersezione di due criteri. Vengono presi in considerazione solo gli elementi che corrispondono a tutti i criteri.
* OPPURE: un&#39;unione di due criteri. Vengono considerati gli elementi che corrispondono ad almeno uno dei due criteri.

![](../assets/journey64.png)

Se utilizzi il [Servizio di segmentazione di Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html) per creare i segmenti, puoi sfruttarli nelle condizioni del percorso. Fai riferimento a [Utilizzo dei segmenti nelle condizioni](../segment/using-a-segment.md).


>[!NOTE]
>
>Non è possibile eseguire query su serie temporali (ad esempio un elenco di acquisti, clic passati sui messaggi) con il semplice editor. A questo scopo, devi utilizzare l’editor avanzato. Consulta [questa pagina](../expression/expressionadvanced.md).

Quando si verifica un errore in un’azione o in una condizione, il percorso di un singolo utente si arresta. L’unico modo per far sì che continui è selezionare la casella **[!UICONTROL Add an alternative path in case of a timeout or an error]** (Aggiungi percorso alternativo in caso di errore o timeout). Vedi [questa sezione](../building-journeys/using-the-journey-designer.md#paths).

## Condizione Origine dati {#data_source_condition}

Ciò ti consente di definire una condizione basata sui campi delle origini dati o degli eventi precedentemente posizionati nel percorso. Per scoprire come utilizzare l’editor di espressioni, consulta [questa pagina](../expression/expressionadvanced.md). Utilizzando l’editor di espressioni avanzate, puoi impostare condizioni più avanzate che manipolano le raccolte o utilizzano origini dati che richiedono il passaggio di parametri. Consulta [questa pagina](../datasource/external-data-sources.md).

![](../assets/journey50.png)

## Condizione di tempo{#time_condition}

Questo consente di eseguire azioni diverse in base all’ora del giorno e/o al giorno della settimana. Ad esempio, puoi decidere di inviare messaggi SMS durante il giorno e e-mail di notte nei giorni feriali.

>[!NOTE]
>
>Il fuso orario non è più specifico per una condizione e ora è definito a livello di percorso nelle proprietà del percorso. Consulta [questa pagina](../building-journeys/timezone-management.md).

![](../assets/journey51.png)

## Divisione percentuale {#percentage_split}

Questa opzione ti consente di suddividere il pubblico in modo casuale per definire un’azione diversa per ciascun gruppo. Definire il numero di suddivisioni e la partizione per ciascun percorso. Il calcolo della suddivisione è statistico, in quanto il sistema non è in grado di prevedere quante persone fluiranno in questa attività del percorso. Di conseguenza, la suddivisione presenta un margine di errore molto basso. Questa funzione è basata su un meccanismo casuale Java (consulta questa [pagina](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)).

>[!NOTE]
>
>Tieni presente che non esiste un pulsante per aggiungere un percorso nella condizione di suddivisione in percentuale. Il numero di percorsi dipenderà dal numero di suddivisioni. In condizioni di suddivisione, non è possibile aggiungere un percorso per altri casi in quanto non può accadere. Le persone entreranno sempre in uno dei percorsi divisi.

![](../assets/journey52.png)

## Condizione data {#date_condition}

Questo ti consente di definire un flusso diverso in base alla data. Ad esempio, se la persona immette il passaggio durante il periodo &quot;vendite&quot;, gli invierai un messaggio specifico. Il resto dell&#39;anno, manderà un altro messaggio.

>[!NOTE]
>
>Il fuso orario non è più specifico per una condizione e ora è definito a livello di percorso nelle proprietà del percorso. Consulta [questa pagina](../building-journeys/timezone-management.md).

![](../assets/journey53.png)
