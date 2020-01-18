---
title: Configurazione delle origini dati
description: Scopri come configurare l’origine dati per il viaggio caso di utilizzo avanzato
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Configurazione delle origini dati {#concept_vml_hdy_w2b}

Nel nostro caso d&#39;uso, vogliamo utilizzare dati di personalizzazione per i nostri messaggi. Dobbiamo anche verificare se la persona è un membro fedeltà e non è stata contattata nelle ultime 24 ore. Queste informazioni sono memorizzate nel database del profilo cliente in tempo reale. L’utente **** tecnico deve configurare l’origine dati della piattaforma Experience per recuperare tali campi.

Per ulteriori informazioni sulla configurazione dell&#39;origine dati, fare riferimento a [](../datasource/about-data-sources.md).

1. Nel menu principale, fate clic sulla **[!UICONTROL Data Sources]**scheda e selezionate l&#39;origine dati integrata della piattaforma Experience.

   ![](../assets/journey23.png)

1. Nei campi gruppo preconfigurati, verificate che siano selezionati i campi seguenti:

   * _Persona > nome > firstName_
   * _persona > nome > lastName_
   * _personalEmail > address_

1. Fate clic **[!UICONTROL Add a New Field Group]**, selezionate uno**[!UICONTROL Profiles]** schema e aggiungete il campo **Fedeltà membro** per la condizione. Il campo **Fedeltà membro** è un campo personalizzato ed è stato aggiunto in XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Fai clic **[!UICONTROL Add a New Field Group]**, seleziona uno**[!UICONTROL ExperienceEvent]** schema e scegli i campi necessari per la nostra condizione in base al numero di messaggi inviati in un determinato periodo: marca _temporale_ per la data e _directMarketing > invia > valore_ per il numero di messaggi inviati.

   ![](../assets/journeyuc2_7.png)

1. Clic **[!UICONTROL Save]**.

Dobbiamo anche verificare se la persona ha una prenotazione nel sistema di prenotazione alberghiera. L&#39;utente **** tecnico deve configurare una seconda origine dati per recuperare questo campo.

1. Nell&#39;elenco delle origini dati, fare clic **[!UICONTROL Add]**per aggiungere una nuova origine dati esterna per definire la connessione al sistema di prenotazione alberghiera.

   ![](../assets/journeyuc2_9.png)

1. Inserite un nome per l’origine dati e l’URL del servizio esterno, ad esempio: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >È consigliabile utilizzare HTTPS per motivi di sicurezza.

1. Configurare l&#39;autenticazione in base alla configurazione del servizio esterno: **[!UICONTROL No authentication]**,**[!UICONTROL Basic]**, **[!UICONTROL Custom]**o**[!UICONTROL API key]**. Nel nostro esempio, scegliamo &quot;Base&quot; per il tipo e specifichiamo il nome utente e la password per la chiamata API.

   ![](../assets/journeyuc2_10.png)

1. Fate clic **[!UICONTROL Add a New Field Group]**per definire le informazioni da recuperare e i parametri API. Per il nostro esempio, esiste un solo parametro (l&#39;id), quindi è necessario creare un gruppo di campi con le seguenti informazioni:

   * **[!UICONTROL Method]**: selezionate il metodo POST o GET. Nel nostro caso, selezioniamo il metodo GET.
   * **[!UICONTROL Cache duration]**: questo varia in base alla frequenza delle chiamate API. Nel nostro caso, il sistema di prenotazione viene aggiornato ogni 10 minuti.
   * **[!UICONTROL Response Payload]**: fare clic all&#39;interno del**[!UICONTROL Payload]** campo e incollare un esempio del payload. Verificare che i tipi di campo siano corretti. Ogni volta che viene chiamata l&#39;API, il sistema recupererà tutti i campi inclusi nell&#39;esempio di payload. Nel nostro esempio, il payload contiene solo lo stato della prenotazione:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: immettete il parametro corrispondente alla chiave utilizzata per identificare ogni cliente, &quot;id&quot; nel nostro esempio. Il valore di questo parametro verrà definito nel percorso.
   ![](../assets/journeyuc2_11.png)

1. Clic **[!UICONTROL Save]**.

   Le origini dati ora sono configurate e pronte per essere utilizzate durante il viaggio.
