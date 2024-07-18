---
product: adobe campaign
title: Metriche e dimensioni
description: Scopri le dimensioni e le metriche disponibili per Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: f6897011-0a5e-4094-a18e-ba2aa25f902c
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 3%

---

# Metriche e dimensioni {#concept_rfj_wpt_52b}

>[!NOTE]
>
>I dati di consegna verranno compilati solo se si dispone di Adobe Campaign Standard.

Qui puoi trovare l’elenco di tutti i componenti disponibili nei rapporti dinamici, oltre alle relative definizioni.

La tabella seguente fornisce l’elenco delle dimensioni utilizzate nei rapporti sul percorso e le relative definizioni.

Per ulteriori informazioni sulla compatibilità tra dimensioni e metriche, consulta [questa pagina](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Dimensioni percorso {#MBE_table_wk4_bnj_w2b}

La tabella seguente fornisce l’elenco delle dimensioni utilizzate nei rapporti sui percorsi, le relative definizioni e formule.

| Dimensioni | Definizione |
|--- |--- |
| **Azione** | Elenco di ogni azione (**nome azione - etichetta azione**) utilizzata nei percorsi. Esempio: Push - Conferma estrazione, E-mail - Fedeltà premi. |
| **Origine dati** | Elenco di origini dati (**nome origine dati**) utilizzate per arricchire i dati in un percorso, ad esempio Adobe Experience Platform, Sistema di prenotazione. |
| **[!UICONTROL Event]** | Elenco di ogni evento (**nome evento - etichetta evento**) utilizzato in percorsi, ad esempio evento Geometrixx - Geometrixx. |
| **Gruppo di campi** | Elenco dei gruppi di campi (**nome gruppo di campi**) utilizzati per arricchire i dati nei percorsi, ad esempio gruppo di campi Profilo, Geometrixx di prenotazione. |
| **Percorso** | Elenco di ogni percorso (**nome percorso**) in modalità di test e live, ad esempio abbandono del carrello, notifica di prenotazione dell&#39;hotel. |
| **versione Percorso** | Elenco di tutte le versioni pubblicate di un percorso (**nome percorso + numero versione**), ad esempio abbandono carrello v1, notifica prenotazione hotel v2. |
| **Orchestrazione** | Elenco di ogni attività di orchestrazione (**Condition, End, Wait**) definita e utilizzata in percorsi. |

## Dimensioni di consegna {#delivery-dimensions}

La tabella seguente fornisce l’elenco delle dimensioni di consegna utilizzate nei rapporti sui percorsi, le relative definizioni e formule.

| Dimensione | Definizione |
|--- |--- |
| **Browser** | Browser da cui è stato aperto o selezionato il messaggio. |
| **Nome consegna** | Etichetta e ID della consegna. |
| **Dispositivo** | Dispositivo da cui è stata aperta/visualizzata/cliccata la notifica e-mail/SMS/push. |
| **Tipo di messaggio** | Canale utilizzato per la consegna, ad esempio e-mail, SMS, notifiche push o in-app. |
| **Nome app mobile** | Nome dell’app mobile |
| **Piattaforma** | Piattaforma del dispositivo da cui è stato aperto/visualizzato/su cui è stato fatto clic il messaggio. |
| **[!UICONTROL Push platform]** | Platform del dispositivo da cui è stata aperta la notifica push, ad esempio iOS o Android. |
| **Dominio destinatario** | Dominio utilizzato per aprire l’e-mail. |
| **URL di tracciamento** | URL su cui l’utente ha fatto clic dal messaggio. |
| **Categoria URL di tracciamento** | Categoria assegnata all’URL di tracciamento. |
| **Etichetta URL di tracciamento** | Etichetta fornita all’URL, ad esempio pagina mirror, contattaci o apri. |
| **Variante** | Variante dell’e-mail in caso di test A/B. |

## Metriche di percorso {#MBE_p_p22_c4j_w2b}

La tabella seguente fornisce l’elenco delle metriche utilizzate nei rapporti sui percorsi, le relative definizioni e formule.

| Metrica | Definizione |
|--- |---|
| **Completato** | Numero totale di individui che hanno terminato normalmente il percorso. |
| **Percentuale di completamento** | Numero totale di individui che terminano normalmente il percorso rispetto al numero totale di individui che entrano nel percorso. |
| **Corrente** | Numero totale di individui attualmente nel percorso, ovvero quante persone sono entrate meno persone che sono uscite, errori e timeout. |
| **Tariffa corrente** | Numero totale di individui attualmente nel percorso rispetto al numero di individui che sono entrati nel percorso. |
| **Inserito** | Numero totale di eventi che hanno avviato una singola voce nel percorso. |
| **Errore** | Numero totale di errori che si sono verificati durante un percorso ma non hanno impedito il completamento del percorso. |
| **Errore nell&#39;azione** | Numero totale di errori che si sono verificati per le azioni. |
| **Errore nell&#39;arricchimento** | Numero totale di errori che si sono verificati per un arricchimento dei dati durante la chiamata di un’origine dati o di un gruppo di campi. |
| **Errore nell&#39;evento** | Numero totale di errori che si sono verificati per gli eventi. |
| **Percentuale errori** | Numero totale di errori che si sono verificati durante un percorso rispetto al numero totale di occorrenze nel percorso. |
| **Azione eseguita** | Numero totale di azioni eseguite per un percorso. |
| **Arricchimento Eseguito** | Numero totale di arricchimenti eseguiti chiamando un’origine dati per ottenere gruppi di campi specifici. |
| **Evento eseguito** | Numero totale di azioni eseguite per un percorso. |
| **Orchestrazione eseguita** | Numero totale di oggetti di orchestrazione (fine, attesa, condizione) eseguiti per un percorso. |
| **Non riuscito** | Numero totale di percorsi non eseguiti correttamente. |
| **Frequenza errori** | Numero totale di percorsi non eseguiti correttamente rispetto al numero di percorsi di esecuzione. |

## Metriche di consegna {#delivery-metrics}

La tabella seguente fornisce l’elenco delle metriche utilizzate nel percorso
i rapporti, le relative definizioni e formule.

| Metrica | Definizione |
|--- |--- |
| **Su elenco Bloccati** | Numero di destinatari che hanno dichiarato un’e-mail come spam o posta indesiderata. |
| **Tasso di Elenchi Bloccati** | Numero totale di messaggi su cui è stato eseguito il inserisco nell&#39;elenco Bloccati di rispetto ai messaggi inviati. |
| **Mancati recapiti + errori** | Totale degli errori accumulati durante la consegna e l’elaborazione automatica dei messaggi restituiti rispetto al numero totale di messaggi inviati. |
| **Mancato recapito + tasso di errore** | Numero totale di messaggi non recapitati rispetto ai messaggi inviati. |
| **Clic** | Numero di volte in cui è stato fatto clic su un contenuto in una consegna. |
| **Percentuale di click-through** | Numero totale di clic in una consegna rispetto al numero di messaggi consegnati. |
| **Consegnato** | Numero di messaggi inviati correttamente, in relazione al numero totale di messaggi inviati. |
| **Percentuale di consegna** | Numero totale di messaggi consegnati correttamente rispetto ai messaggi inviati. |
| **Errore** | Numero totale di errori che si sono verificati durante un percorso ma non hanno impedito il completamento del percorso. |
| **Mancato recapito permanente** | Numero totale di errori permanenti, ad esempio un indirizzo e-mail errato. |
| **Percentuale mancati recapiti permanenti** | Numero totale di consegne non riuscite a causa di errori permanenti rispetto ai messaggi inviati. |
| **Pagina mirror** | Numero di destinatari che hanno fatto clic sul collegamento della pagina speculare. |
| **Frequenza pagine mirror** | Numero totale di clic sul collegamento della pagina speculare rispetto al totale dei messaggi consegnati. |
| **Open** | Numero di volte in cui un messaggio è stato aperto in una consegna. |
| **Percentuale aperture** | Numero totale di messaggi aperti rispetto al numero di messaggi consegnati. |
| **Quarantena** | Numero di messaggi non recapitati che hanno portato alla quarantena dell’indirizzo. |
| **Frequenza quarantena** | Numero totale di quarantene rispetto ai messaggi inviati. |
| **Rifiutato** | Numero di messaggi classificati come spam dai server SMTP. |
| **Tasso rifiutato** | Numero totale di messaggi contrassegnati come rifiutati rispetto ai messaggi inviati. |
| **Elaborato/inviato** | Numero totale di invii per la consegna. |
| **Mancato recapito non permanente** | Numero totale di errori temporanei, ad esempio una casella in entrata completa. |
| **Percentuale mancati recapiti non permanenti** | Numero totale di consegne non riuscite per motivi temporanei rispetto ai messaggi inviati. |
| **Clic univoci** | Numero di destinatari che hanno fatto clic su un contenuto in una consegna. |
| **Aperture univoche** | Numero di destinatari che hanno aperto la consegna. |
| **Abbonamento annullato** | Numero di clic sul collegamento di annullamento dell’abbonamento. |
| **Percentuale annullamenti abbonamento** | Numero totale di annullamenti di abbonamenti per destinatario rispetto ai messaggi consegnati. |
