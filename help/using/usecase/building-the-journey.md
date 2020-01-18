---
title: Costruire il viaggio
description: 'Scopri come creare il percorso avanzato per l’utilizzo dei casi '
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


# Costruire il viaggio {#concept_owm_kdy_w2b}

L&#39;utente **** aziendale ora può costruire il percorso. Il nostro viaggio includerà le seguenti attività:

* due **[!UICONTROL Event]**attività: &quot;LobbyBeacon&quot; e &quot;RestaurantBeacon&quot;
* due **[!UICONTROL Condition]**attività
* tre **[!UICONTROL Push]**attività e una**[!UICONTROL Email]** attività (utilizzando Adobe Campaign Standard)
* un&#39; **[!UICONTROL Wait]**attività
* quattro **[!UICONTROL End]**attività

>[!NOTE]
>
>Le attività **[!UICONTROL Push]**e**[!UICONTROL Email]** sono disponibili nella palette solo se disponete di Adobe Campaign Standard.

Per ulteriori informazioni su come costruire un viaggio, consulta [](../building-journeys/journey.md).

## Primi passi{#section_ntb_ws1_ffb}

1. Nel menu superiore, fai clic sulla **[!UICONTROL Home]**scheda e**[!UICONTROL Create]** crea un nuovo percorso.

   ![](../assets/journey31.png)

1. Modifica le proprietà del viaggio nel riquadro di configurazione visualizzato sul lato destro. Aggiungete un nome e impostatelo per la durata di un mese, dal 1 al 31 dicembre.

   ![](../assets/journeyuc2_12.png)

1. Iniziate a progettare il viaggio trascinando l’evento &quot;LobbyBeacon&quot; dalla palette al quadro. È inoltre possibile fare doppio clic sull&#39;evento nella palette per aggiungerlo al quadro.

   ![](../assets/journeyuc2_13.png)

1. Aggiungiamo ora una condizione per verificare che la persona non sia stata contattata nelle ultime 24 ore e verificare se è un membro fedeltà. Trascina e rilascia un’attività di condizione nel percorso.

   ![](../assets/journeyuc2_14.png)

1. Scegliete il **[!UICONTROL Data Source Condition]**tipo e fate clic nel**[!UICONTROL Expression]** campo. È inoltre possibile definire un&#39;etichetta di condizione che verrà visualizzata sulla freccia, nel quadro. Nel nostro esempio, sostituiamo &quot;Condizione 1&quot; con &quot;Fedeltà membro&quot;.

   ![](../assets/journeyuc2_15.png)

1. Fai clic su **[!UICONTROL Advanced mode]**e definisci la seguente condizione in base ai campi &quot;timestamp&quot; e &quot;directMarketing.send.value&quot; provenienti dall’origine dati della Piattaforma esperienza. La sintassi dell&#39;espressione è la seguente:

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
   and
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   ![](../assets/journeyuc2_30.png)

1. Fate clic sul **[!UICONTROL Add a path]**pulsante e create un secondo percorso per i clienti che non sono stati contattati nelle ultime 24 ore e non sono membri fedeltà. Denominate il percorso &quot;Not Fealty Member&quot; (Non membro fedeltà). La sintassi dell&#39;espressione è la seguente:

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days").timestamp}) == 0
   and not
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   >[!NOTE]
   >
   >Nella seconda parte dell&#39;espressione, &quot;Profile&quot; è facoltativo.

1. È necessario selezionare uno spazio dei nomi. Uno spazio dei nomi è preselezionato in base alle proprietà dello schema. È possibile mantenere quello preselezionato. Per ulteriori informazioni sugli spazi dei nomi, vedere [](../event/selecting-the-namespace.md).

Nel nostro caso d&#39;uso, vogliamo solo reagire a queste due condizioni, quindi non controlliamo la casella **[!UICONTROL Show path for other cases than the one(s) above]**.

Dopo la condizione vengono creati due percorsi:

* _Clienti che non sono stati contattati nelle ultime 24 ore e che sono membri fedeltà._
* _Clienti che non sono stati contattati nelle ultime 24 ore e che non sono membri fedeltà._

![](../assets/journeyuc2_16.png)

## Primo percorso: il cliente è un membro fedeltà {#section_otb_ws1_ffb}

1. Nel primo percorso, aggiungiamo una condizione per verificare se ha una prenotazione. Trascina e rilascia un’attività di condizione nel percorso.

   ![](../assets/journeyuc2_17.png)

1. Scegliere il **[!UICONTROL Data Source Condition]**tipo e definire la condizione in base alle informazioni sullo stato della prenotazione recuperate dal sistema di prenotazione:

   ```
   #{MarltonReservation.MarltonFieldGroup.reservation} == true
   ```

   ![](../assets/journeyuc2_18.png)

1. Quando si seleziona un campo da un&#39;origine dati esterna, nella parte destra della schermata viene visualizzato l&#39;elenco dei parametri definiti al momento della configurazione dell&#39;origine dati esterna (vedere [](../usecase/configuring-the-data-sources.md)). Fai clic sul nome del parametro e definisci il valore della chiave del sistema di prenotazione, il Experience Cloud ID, nel nostro esempio:

   ```
   @{LobbyBeacon.endUserIDs._experience.mcid.id}
   ```

   ![](../assets/journeyuc2_19.png)

1. Dal momento che vogliamo reagire anche ai clienti che non hanno una prenotazione, dobbiamo controllare la casella **[!UICONTROL Show path for other cases than the one(s) above]**.

   ![](../assets/journeyuc2_20.png)

   Vengono creati due percorsi:

   * _Clienti che hanno prenotato una stanza_
   * _Clienti che non hanno prenotato una stanza._
   ![](../assets/journeyuc2_21.png)

1. Nel primo percorso (stanza prenotata), lasciate cadere un&#39; **[!UICONTROL Push]**attività, selezionate la vostra app mobile e il modello di &quot;Benvenuto&quot;.

   ![](../assets/journeyuc2_22.png)

1. Definite i **[!UICONTROL Target]**campi richiesti dal sistema per inviare il push.

   * **[!UICONTROL Push platform]**: selezionate la piattaforma:**[!UICONTROL Apple Push Notification Server]** (Apple) o **[!UICONTROL Firebase Cloud Messaging]**(Android).
   * **[!UICONTROL Registration token]**: aggiungete la seguente espressione (basata sull&#39;evento configurato) utilizzando la modalità avanzata:

      ```
      @{LobbyBeacon._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
      ``
      
1. Definite i campi di personalizzazione delle notifiche push. Nel nostro esempio: nome e cognome.

1. Aggiungete un evento &quot;RestaurantBeacon&quot;.

   ![](../assets/journeyuc2_23.png)

1. Aggiungete una nuova **[!UICONTROL Push]**attività, selezionate il modello &quot;Sconto pasti&quot; e definite i**[!UICONTROL Address]** campi e **[!UICONTROL Personalization]**. Aggiungete un&#39;**[!UICONTROL End]** attività.

   ![](../assets/journeyuc2_24.png)

1. Vogliamo inviare una notifica push con sconto pasto solo se la persona entra nel ristorante entro le prossime 6 ore dopo la push di benvenuto. A tal fine, è necessario utilizzare un&#39;attività di attesa. Posizionate il cursore sull&#39;attività push di benvenuto e fate clic sul simbolo &quot;+&quot;. Nel nuovo percorso, aggiungete un&#39;attività di attesa e definite una durata di 6 ore. Sarà scelta la prima attività ammissibile. Se l’evento del ristorante viene ricevuto meno di 6 ore dopo il push di benvenuto, l’attività push viene inviata. Se non viene ricevuto nessun evento del ristorante entro le prossime 6 ore, l&#39;attesa viene scelta. Inserite un&#39; **[!UICONTROL End]**attività dopo l&#39;attività di attesa.

   ![](../assets/journeyuc2_31.png)

1. Nel secondo percorso che segue la condizione di prenotazione (nessuna stanza prenotata), aggiungete un&#39; **[!UICONTROL Push]**attività e selezionate il modello &quot;Tariffe camera&quot;. Aggiungete un&#39;**[!UICONTROL End]** attività.

   ![](../assets/journeyuc2_25.png)

## Secondo percorso: il cliente non è un membro fedeltà{#section_ptb_ws1_ffb}

1. Nel secondo percorso che segue la prima condizione (il cliente non è un membro fedeltà), aggiungete un&#39; **[!UICONTROL Email]**attività e selezionate il modello di &quot;iscrizione fedeltà&quot;.

   ![](../assets/journeyuc2_26.png)

1. Nel **[!UICONTROL Address]**campo, selezionare l&#39;indirizzo e-mail dall&#39;origine dati.

   ![](../assets/journeyuc2_27.png)

1. Definire i campi di personalizzazione del nome e del cognome dall&#39;origine dati.

   ![](../assets/journeyuc2_28.png)

1. Aggiungete un&#39; **[!UICONTROL End]**attività.

Fai clic sull&#39; **[!UICONTROL Test]**interruttore e verifica il percorso. In caso di errore, disattivate la modalità di prova, modificate il percorso e verificatene di nuovo il funzionamento. Per ulteriori informazioni sulla modalità di prova, vedere[](../building-journeys/testing-the-journey.md).

![](../assets/journeyuc2_32bis.png)

Quando il test è conclusivo, potete pubblicare il viaggio dal menu a discesa in alto a destra.

![](../assets/journeyuc2_32.png)
