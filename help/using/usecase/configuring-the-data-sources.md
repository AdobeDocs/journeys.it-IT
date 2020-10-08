---
title: Configurazione delle origini dati
description: Scopri come configurare l’origine dati per il percorso, caso di utilizzo avanzato
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
source-wordcount: '457'
ht-degree: 14%

---


# Configurazione delle origini dati {#concept_vml_hdy_w2b}

Nel nostro caso d&#39;uso, vogliamo utilizzare dati di personalizzazione per i nostri messaggi. Dobbiamo anche verificare se la persona è un membro fedeltà e non è stata contattata nelle ultime 24 ore. Queste informazioni sono memorizzate nel database del profilo cliente in tempo reale. L&#39;utente **** tecnico deve configurare l&#39;origine dati Adobe Experience Platform per recuperare tali campi.

Per ulteriori informazioni sulla configurazione dell&#39;origine dati, fare riferimento a [](../datasource/about-data-sources.md).

1. Nel menu principale, fare clic sulla **[!UICONTROL Data Sources]** scheda e selezionare l&#39;origine dati Adobe Experience Platform incorporata.

   ![](../assets/journey23.png)

1. Nei campi gruppo preconfigurati, verificate che siano selezionati i campi seguenti:

   * _Persona > nome > firstName_
   * _persona > nome > lastName_
   * _personalEmail > address_

1. Fate clic **[!UICONTROL Add a New Field Group]**, selezionate uno **[!UICONTROL Profiles]** schema e aggiungete il campo **Fedeltà membro** per la condizione. Il campo **Fedeltà membro** è un campo personalizzato ed è stato aggiunto in XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Fai clic **[!UICONTROL Add a New Field Group]**, seleziona uno **[!UICONTROL ExperienceEvent]** schema e scegli i campi necessari per la nostra condizione, in base al numero di messaggi inviati in un determinato periodo: _marca_ temporale per la data e _directMarketing > invia > valore_ per il numero di messaggi inviati.

   ![](../assets/journeyuc2_7.png)

1. Fai clic su **[!UICONTROL Save]**.

Dobbiamo anche verificare se la persona ha una prenotazione nel sistema di prenotazione alberghiera. L&#39;utente **** tecnico deve configurare una seconda origine dati per recuperare questo campo.

1. Nell&#39;elenco delle origini dati, fare clic **[!UICONTROL Add]** per aggiungere una nuova origine dati esterna per definire la connessione al sistema di prenotazione alberghiera.

   ![](../assets/journeyuc2_9.png)

1. Inserite un nome per l’origine dati e l’URL del servizio esterno, ad esempio: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >Per motivi di sicurezza, è consigliabile utilizzare HTTPS.

1. Imposta l’autenticazione in base alla configurazione del servizio esterno: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** o **[!UICONTROL API key]**. Nel nostro esempio, scegliamo &quot;Base&quot; per il tipo e specifichiamo il nome utente e la password per la chiamata API.

   ![](../assets/journeyuc2_10.png)

1. Fate clic **[!UICONTROL Add a New Field Group]** per definire le informazioni da recuperare e i parametri API. Per il nostro esempio, esiste un solo parametro (l&#39;id), quindi è necessario creare un gruppo di campi con le seguenti informazioni:

   * **[!UICONTROL Method]**: seleziona il metodo POST o GET. Nel nostro caso, scegliamo il metodo GET.
   * **[!UICONTROL Cache duration]**: questo varia in base alla frequenza delle chiamate API. Nel nostro caso, il sistema di prenotazione viene aggiornato ogni 10 minuti.
   * **[!UICONTROL Response Payload]**: fare clic all&#39;interno del **[!UICONTROL Payload]** campo e incollare un esempio del payload. Verifica la correttezza dei tipi di campi. Ogni volta che viene chiamata l’API, il sistema recupererà tutti i campi inclusi nell’esempio di payload. Nel nostro esempio, il payload contiene solo lo stato della prenotazione:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: immettete il parametro corrispondente alla chiave utilizzata per identificare ogni cliente, &quot;id&quot; nel nostro esempio. Il valore di questo parametro verrà definito nel percorso.

   ![](../assets/journeyuc2_11.png)

1. Fai clic su **[!UICONTROL Save]**.

   Le origini dati ora sono configurate e pronte per essere utilizzate durante il viaggio.
