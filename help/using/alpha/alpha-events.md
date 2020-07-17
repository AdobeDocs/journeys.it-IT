---
title: Eventi basati su regole
description: Ulteriori informazioni sugli eventi basati su regole.
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
source-git-commit: a65a5db5b35291cbc2635f9ae67fd8c8c5284575
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 6%

---


# Eventi basati su regole{#simplified-events}

Abbiamo semplificato la configurazione degli eventi di esperienza. Stiamo introducendo un nuovo metodo che non richiede l&#39;uso di un eventID. Quando configurate l&#39;evento in Journey Orchestration, ora potete definire un evento basato su regole.

Questo nuovo tipo di evento non genera un eventID. Utilizzando l&#39;editor di espressioni semplici, ora è sufficiente definire una regola che verrà utilizzata dal sistema per identificare gli eventi rilevanti che attiveranno i vostri viaggi. Questa regola può essere basata su qualsiasi campo disponibile nel payload dell&#39;evento, ad esempio la posizione del profilo o il numero di elementi aggiunti al carrello del profilo.

Questo nuovo metodo è per lo più trasparente per gli utenti. L’unica modifica è un nuovo campo nella schermata di definizione dell’evento.

1. Dal menu a sinistra, fate clic sull&#39; **[!UICONTROL Admin]** icona, quindi fate clic su **[!UICONTROL Events]**. Viene visualizzato l’elenco degli eventi.

   ![](../assets/alpha-event1.png)

1. Per creare un nuovo evento, fai clic su **[!UICONTROL Add]**. Il riquadro di configurazione dell’evento si apre sul lato destro dello schermo.

   ![](../assets/alpha-event2.png)

1. Immettete il nome dell’evento. Potete anche aggiungere una descrizione.

   ![](../assets/alpha-event3.png)

1. Nel nuovo **[!UICONTROL Event ID type]** campo, selezionare **[!UICONTROL Rule Based]**.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >Il **[!UICONTROL System Generated]** tipo è il metodo esistente che richiede un eventID. Vedere [questa sezione](../event/about-events.md).

1. Definire il **[!UICONTROL Schema]** e il payload **[!UICONTROL Fields]**. Vedere [questa sezione](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >Quando selezionate l&#39; **[!UICONTROL System Generated type]**, sono disponibili solo gli schemi che hanno il tipo eventID mixin. Quando selezionate il **[!UICONTROL Rule Based]** tipo, sono disponibili tutti gli schemi di eventi esperienza.

1. Fare clic all&#39;interno del **[!UICONTROL Event ID condition]** campo. Utilizzando l&#39;editor di espressioni semplici, definire la condizione che verrà utilizzata dal sistema per identificare gli eventi che attiveranno il percorso.

   ![](../assets/alpha-event6.png)

   Nel nostro esempio, abbiamo scritto una condizione basata sulla città del profilo. Ciò significa che ogni volta che il sistema riceve un evento che corrisponde a questa condizione (**[!UICONTROL City]** campo e **[!UICONTROL Paris]** valore), lo trasmette ad Journey Orchestration.

1. Definite il **[!UICONTROL Namespace]** e **[!UICONTROL Key]**. Consultate [Selezione dello spazio dei nomi](../event/selecting-the-namespace.md) e [Definizione della chiave](../event/defining-the-event-key.md)evento.

   ![](../assets/alpha-event7.png)

Gli altri passaggi per la configurazione degli eventi e la creazione del percorso restano invariati.

L&#39;evento è ora configurato e pronto per essere rilasciato come qualsiasi altro evento. Ogni volta che un evento corrispondente alla regola viene inviato al sistema, viene passato ad Journey Orchestration per attivare i viaggi.

