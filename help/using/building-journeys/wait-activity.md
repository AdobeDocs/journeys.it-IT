---
title: Attendi attività
description: Ulteriori informazioni sull'attività di attesa
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
source-git-commit: 6274426ec04315149fb430b847498c0e20164bae

---


# Attendi attività{#section_rlm_nft_dgb}

Se desiderate aspettare prima di eseguire l&#39;attività successiva nel percorso, potete utilizzare un&#39; **[!UICONTROL Wait]** attività. Consente di definire il momento in cui verrà eseguita l&#39;attività successiva. Sono disponibili quattro opzioni:

* [Durata](#duration)
* [Data fissa](#fixed_date)
* [Personalizzato](#custom)
* [Ottimizzazione dell&#39;ora di invio tramite e-mail](#email_send_time_optimization)

## Informazioni sull&#39;attività Wait{#about_wait}

Di seguito viene illustrata la priorità delle attese quando si utilizzano più attese in parallelo. Se hanno la stessa configurazione temporale e una condizione diversa ma sovrapposta, l&#39;attesa posizionata sopra sarà quella con priorità. Ad esempio, la condizione della prima attesa è &quot;essere una donna&quot; e la condizione della seconda attesa in parallelo è &quot;essere una VIP&quot;. La priorità della prima attività di attesa

Inoltre, se due diverse attese sono in parallelo, quella che si verifica per prima verrà definita come priorità, indipendentemente dalla posizione verticale. Ad esempio, se un’attesa di 1 ora è superiore e un’attesa di 30 minuti è inferiore, dopo 30 minuti verrà elaborata l’attesa di 30 minuti.

È possibile definire una condizione se si desidera limitare l&#39;attesa a una determinata popolazione.

>[!NOTE]
>
>La durata massima di attesa è di 30 giorni.
>
>In modalità di prova, il parametro Tempo di **attesa nel test** consente di definire l&#39;ora in cui ciascuna attività di attesa durerà. Il tempo predefinito è 10 secondi. In questo modo sarà possibile ottenere rapidamente i risultati del test. Vedere [](../building-journeys/testing-the-journey.md)

## Durata{#duration}

Selezionate la durata dell&#39;attesa prima dell&#39;esecuzione dell&#39;attività successiva.

![](../assets/journey55.png)

## Attesa data fissa{#fixed_date}

Selezionare la data per l&#39;esecuzione dell&#39;attività successiva. Quando si definisce una data fissa, è necessario specificare un fuso orario. Vedere [](../building-journeys/timezone-management.md).

![](../assets/journey56.png)

## Attesa personalizzata{#custom}

Questa opzione consente di definire una data personalizzata, ad esempio 12 luglio 2020 alle 17:00, utilizzando un&#39;espressione avanzata basata su un campo proveniente da un evento o un&#39;origine dati. Non consente di definire una durata personalizzata, ad esempio 7 giorni. L&#39;espressione nell&#39;editor di espressioni deve fornire un formato dateTimeOnly. Vedere [](../expression/expressionadvanced.md). Per ulteriori informazioni sul formato dateTimeOnly, vedi [](../expression/data-types.md)

>[!NOTE]
>
>È possibile utilizzare un&#39;espressione dateTimeOnly o una funzione per convertire in dateTimeOnly. Ad esempio: toDateTimeOnly(@{Event.offerOpened.activity.endTime}), il campo nell&#39;evento che si trova nel modulo 2016-08-12T09:46:06.
>
>Il fuso **** orario è previsto in un&#39;altra posizione nel riquadro di configurazione dell&#39;attesa personalizzato. Di conseguenza, oggi non è possibile dall&#39;interfaccia puntare direttamente a un tempo di mixaggio e un fuso orario ISO-8601 completo come 2016-08-12T09:46:06.982-05. Vedere [](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

## Ottimizzazione dell&#39;ora di invio tramite e-mail{#email_send_time_optimization}

>[!CAUTION]
>
>La funzionalità di ottimizzazione dell&#39;ora di invio tramite e-mail è disponibile solo per i clienti che utilizzano la funzione Adobe Campaign Standard Data Service.

Questo tipo di attesa utilizza un punteggio calcolato nella piattaforma. La valutazione calcola la propensione a fare clic o aprire un messaggio e-mail in futuro in base al comportamento passato. L&#39;algoritmo che calcola il punteggio richiede una certa quantità di dati per funzionare. Di conseguenza, quando non dispone di dati sufficienti, viene applicato il tempo di attesa predefinito. Al momento della pubblicazione, vi verrà notificato che si applica l’ora predefinita.

>[!NOTE]
>
>Il primo evento del viaggio deve avere uno spazio dei nomi.
>
>Questa funzionalità è disponibile solo dopo un&#39; **[!UICONTROL Email]** attività. Devi disporre di Adobe Campaign Standard.

1. Nel **[!UICONTROL Amount of time]** campo, definite il numero di ore da dedicare all’ottimizzazione dell’invio e-mail.
1. Nel **[!UICONTROL Optimization type]** campo, scegliete se l&#39;ottimizzazione deve aumentare i clic o si apre.
1. Nel campo Ora **** predefinita, definire l’ora predefinita da attendere se il punteggio relativo all’ora di invio predittivo non è disponibile.

   >[!NOTE]
   >
   >Il punteggio relativo al tempo di invio potrebbe non essere disponibile perché non sono disponibili dati sufficienti per eseguire il calcolo. In questo caso, al momento della pubblicazione verrà comunicato che si applica l&#39;ora predefinita.

![](../assets/journey57bis.png)
