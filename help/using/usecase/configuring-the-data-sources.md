---
product: adobe campaign
title: Configurazione delle origini dati
description: Scopri come configurare l’origine dati per il caso d’uso avanzato del percorso
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 16%

---

# Configurazione delle origini dati {#concept_vml_hdy_w2b}

Nel nostro caso d’uso, vogliamo utilizzare i dati di personalizzazione per i nostri messaggi. Dobbiamo anche verificare se la persona è un membro fedeltà e non è stata contattata nelle ultime 24 ore. Queste informazioni vengono memorizzate nel database Profilo cliente in tempo reale. Il **utente tecnico** deve configurare l’origine dati Adobe Experience Platform per recuperare tali campi.

Per ulteriori informazioni sulla configurazione dell’origine dati, consulta [questa pagina](../datasource/about-data-sources.md).

1. Nel riquadro del menu, seleziona **[!UICONTROL Admin]**. Dalla sezione **[!UICONTROL Data sources]**, fai clic su **[!UICONTROL Manage]**.
1. Seleziona l’origine dati integrata di Adobe Experience Platform.

   ![](../assets/journey23.png)

1. Nei campi del gruppo preconfigurato, verifica che siano selezionati i campi seguenti:

   * _person > name > firstName_
   * _persona > nome > cognome_
   * _personalEmail > indirizzo_

1. Clic **[!UICONTROL Add a New Field Group]**, seleziona un **[!UICONTROL Profiles]** e aggiungere **Membro fedeltà** per la nostra condizione. Il **Membro fedeltà** è un campo personalizzato ed è stato aggiunto in XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Clic **[!UICONTROL Add a New Field Group]**, seleziona un **[!UICONTROL ExperienceEvent]** e scegli i campi necessari per la condizione sul numero di messaggi inviati in un determinato periodo: _timestamp_ per la data e _directMarketing > invia > valore_ per il numero di messaggi inviati.

   ![](../assets/journeyuc2_7.png)

1. Fai clic su **[!UICONTROL Save]**.

Dobbiamo anche verificare se la persona ha una prenotazione nel sistema di prenotazione dell’hotel. Il **utente tecnico** deve configurare una seconda origine dati per recuperare questo campo.

1. Nell’elenco delle origini dati, fai clic su **[!UICONTROL Add]** per aggiungere una nuova origine dati esterna per definire la connessione al sistema di prenotazione dell’hotel.

   ![](../assets/journeyuc2_9.png)

1. Immetti un nome per l’origine dati e l’URL del servizio esterno, ad esempio: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >Per motivi di sicurezza, è consigliabile utilizzare HTTPS.

1. Imposta l’autenticazione in base alla configurazione del servizio esterno: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** o **[!UICONTROL API key]**. Nel nostro esempio, scegliamo &quot;Base&quot; per il tipo e specifichiamo il nome utente e la password per la chiamata API.

   ![](../assets/journeyuc2_10.png)

1. Clic **[!UICONTROL Add a New Field Group]** per definire le informazioni da recuperare e i parametri API. Nel nostro esempio, esiste un solo parametro (l’ID), pertanto è necessario creare un gruppo di campi con le seguenti informazioni:

   * **[!UICONTROL Method]**: seleziona il metodo POST o GET. Nel nostro caso, scegliamo il metodo GET.
   * **[!UICONTROL Response Payload]**: fai clic all’interno del **[!UICONTROL Payload]** e incolla un esempio del payload. Verifica la correttezza dei tipi di campi. Ogni volta che viene chiamata l’API, il sistema recupererà tutti i campi inclusi nell’esempio di payload. Nel nostro esempio, il payload contiene solo lo stato della prenotazione:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: inserisci il parametro corrispondente alla chiave utilizzata per identificare ogni cliente, &quot;id&quot; nel nostro esempio. Il valore di questo parametro verrà definito nel percorso.

   ![](../assets/journeyuc2_11.png)

1. Fai clic su **[!UICONTROL Save]**.

   Le origini dati sono ora configurate e pronte per essere utilizzate nel percorso.
