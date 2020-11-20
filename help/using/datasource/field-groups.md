---
product: adobe campaign
solution: Journey Orchestration
title: Gruppi di campi
description: Scopri i gruppi di campi
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 0%

---



# Gruppi di campi {#concept_ntl_ypt_52b}

I gruppi di campi sono insiemi di campi che è possibile recuperare da un&#39;origine dati e utilizzare in un percorso.

## Definizione dei gruppi di campi {#section_dsz_kjd_fjb}

Per ogni origine dati, è possibile definire diversi gruppi di campi, ciascuno dei quali ha una specifica durata cache.

Ad esempio, potete creare un gruppo di campi con il numero di telefono, l&#39;e-mail, il nome e l&#39;indirizzo del profilo. Potrai quindi utilizzare questi dati nel tuo viaggio per creare condizioni. Ad esempio, potete decidere di inviare un SMS solo se il numero di telefono del profilo non è vuoto. Se questo campo è vuoto, potete inviare un messaggio e-mail.

Anche se viene aggiunto automaticamente un nome predefinito, si consiglia di assegnare un nome al gruppo di campi. In effetti, il nome del gruppo di campi sarà visibile agli altri utenti in [!DNL Journey Orchestration]. È consigliabile assegnare un nome pertinente ai gruppi di campi.

Quando un campo origine dati viene utilizzato in un percorso, il sistema recupera tutti i campi definiti per quel gruppo di campi. Di conseguenza, è consigliabile selezionare solo i campi necessari per i viaggi. Questo ridurrà la latenza richiesta nei vostri viaggi, aumentando così le prestazioni. È possibile aggiungere facilmente più campi in gruppi di campi in un secondo momento.

**[!UICONTROL Cache duration]** è importante anche in quanto consente di ottimizzare le prestazioni. La durata della cache indica che in un viaggio, se i dati di un gruppo di campi vengono recuperati una volta, il sistema la memorizzerà nella cache temporaneamente. Se gli stessi dati sono richiesti successivamente nello stesso percorso, il sistema non effettuerà un&#39;altra richiesta all&#39;origine dati. La configurazione della durata della cache deve essere adattata per ogni caso di utilizzo. Se avete bisogno di recuperare dati in tempo reale come lo stato di prenotazione dell&#39;hotel, le informazioni meteo o il numero di punti fedeltà, associerete il gruppo di campi che contiene questi campi con una breve durata della cache (ad esempio 1 secondo). Per i campi aggiornati meno frequentemente (nome, genere), create un secondo gruppo di campi con una durata cache più lunga (ad esempio, 5 giorni).

The number of journeys that use a field group is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of journeys using this field group.

>[!NOTE]
>
>Tenere presente che se un gruppo di campi non ha campi, non verrà visualizzato nell&#39;editor di espressioni.

![](../assets/journey3bis.png)

## Ciclo di vita del gruppo di campi {#section_abk_njd_fjb}

È possibile aggiungere o rimuovere campi da un gruppo di campi che non è utilizzato per le operazioni di bozza o di viaggio live.

È possibile aggiungere ma non rimuovere un campo da un gruppo di campi utilizzato in uno o più viaggi bozza o dal vivo. Questo eviterà di interrompere i viaggi.

Per eliminare un campo da un gruppo di campi utilizzato in uno o più viaggi, procedere come segue. Utilizzare un esempio di un gruppo di campi denominato &quot;Gruppo di campi A&quot;.

1. Nell&#39;elenco dei gruppi di campi, posizionate il cursore sul &quot;Gruppo di campi A&quot; e fate clic sull&#39; **[!UICONTROL Duplicate]** icona a destra. Denominate, ad esempio, il gruppo di campi duplicato &quot;Gruppo di campi B&quot;.
1. In &quot;Gruppo di campi B&quot;, rimuovere i campi che non si desidera più.
1. In &quot;Campo Gruppo A&quot;, verificare la posizione in cui viene utilizzato questo gruppo di campi. Queste informazioni vengono visualizzate nel **[!UICONTROL Used in]** campo.
1. Aprire tutti i viaggi che utilizzano il &quot;Campo Gruppo A&quot;.
1. Create nuove versioni di ciascuno di questi viaggi. Modificate tutte le attività utilizzando il &quot;Gruppo di campi A&quot; e selezionate &quot;Gruppo di campi B&quot;.
1. Arrestate le versioni precedenti dei viaggi che utilizzano &quot;Field Group A&quot;. A questo punto non si dovrebbe effettuare alcun viaggio utilizzando il &quot;Gruppo di campi A&quot;.
1. Rimuovere il &quot;Campo Gruppo A&quot; così come non è più utilizzato.
