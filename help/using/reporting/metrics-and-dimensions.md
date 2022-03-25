---
product: adobe campaign
title: Metriche e dimensioni
description: Informazioni su dimensioni e metriche disponibili per il Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: f6897011-0a5e-4094-a18e-ba2aa25f902c
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 2%

---

# Metriche e dimensioni {#concept_rfj_wpt_52b}

>[!NOTE]
>
>I dati di consegna verranno compilati solo se disponi di Adobe Campaign Standard.

Qui puoi trovare l’elenco di tutti i componenti disponibili nei report dinamici e le relative definizioni.

La tabella seguente fornisce l’elenco delle dimensioni utilizzate nei rapporti sui percorsi e le relative definizioni.

Per ulteriori informazioni sulla compatibilità tra dimensioni e metriche, consulta [questa pagina](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Dimensioni percorso {#MBE_table_wk4_bnj_w2b}

La tabella seguente fornisce l’elenco delle dimensioni utilizzate nei rapporti sui percorsi, le relative definizioni e formule.

| Dimensioni | Definizione |
|--- |--- |
| **Azione** | Elenco di ogni azione (**nome azione - etichetta azione**) utilizzata in percorsi come Push - Check-Out Confirm, Email - Rewards fidelity. |
| **Origine dati** | Elenco delle origini dati (**nome origine dati**) utilizzata per arricchire i dati in un percorso, ad esempio Adobe Experience Platform, Sistema di prenotazione. |
| **[!UICONTROL Event]** | Elenco di ogni evento (**nome evento - etichetta evento**) utilizzata in percorsi come ad esempio Geometrixx evento - Geometrixx check-out. |
| **Gruppo di campi** | Elenco dei gruppi di campi (**nome del gruppo di campi**) utilizzata per arricchire i dati in percorsi come il gruppo di campi Profilo e il sistema di prenotazione Geometrixx. |
| **Percorso** | Elenco di ogni percorso (**Nome percorso**) in modalità di prova e live, ad esempio abbandono del carrello, notifica di prenotazione dell&#39;hotel. |
| **Versione percorso** | Elenco di ogni versione pubblicata di un percorso (**Nome percorso + numero della versione**) ad esempio Abbandono del carrello v1, notifica di prenotazione dell&#39;hotel v2. |
| **Orchestrazione** | Elenco di ogni attività di orchestrazione (**Condizione, Fine, Attendi**) definita e utilizzata nei percorsi. |

## Dimensioni di consegna {#delivery-dimensions}

La tabella seguente fornisce l’elenco delle dimensioni di consegna utilizzate nei rapporti sui percorsi, le relative definizioni e formule.

| Dimensione | Definizione |
|--- |--- |
| **Browser** | Browser da cui è stato aperto o su cui è stato fatto clic il messaggio. |
| **Nome consegna** | Etichetta e ID della consegna. |
| **Dispositivo** | Dispositivo da cui è stata aperta/visualizzata/su la notifica e-mail/SMS/push. |
| **Tipo di messaggio** | Canale utilizzato per la consegna, ad esempio e-mail, SMS, notifiche push o in-app. |
| **Nome app Mobile** | Nome dell’app mobile |
| **Piattaforma** | Piattaforma del dispositivo da cui il messaggio è stato aperto, visualizzato o su cui è stato fatto clic. |
| **[!UICONTROL Push platform]** | Piattaforma del dispositivo da cui è stata aperta la notifica push, ad esempio iOS o Android. |
| **Dominio destinatario** | Dominio utilizzato per aprire l’e-mail. |
| **URL di tracciamento** | URL su cui l’utente ha fatto clic dal messaggio. |
| **Categoria URL di tracciamento** | Categoria assegnata all’URL di tracciamento. |
| **Etichetta URL di tracciamento** | Etichetta data all’URL, ad esempio pagina speculare, contattaci o apri. |
| **Variante** | Variante dell’e-mail in caso di test A/B. |

## Metriche di percorso {#MBE_p_p22_c4j_w2b}

La tabella seguente fornisce l’elenco delle metriche utilizzate nei rapporti sui percorsi, le relative definizioni e formule.

| Metrica | Definizione |
|--- |---|
| **Completato** | Numero totale di individui che hanno terminato normalmente il percorso. |
| **Tasso di completamento** | Numero totale di individui che hanno concluso normalmente il percorso rispetto al numero totale di individui che sono entrati nel percorso. |
| **Corrente** | Numero totale di persone attualmente nel percorso, ovvero quante persone sono entrate meno persone che sono uscite, errori e timeout. |
| **Tasso attuale** | Numero totale di persone attualmente nel percorso rispetto al numero di persone che sono entrate nel percorso. |
| **Inserito** | Numero totale di eventi che si sono verificati per avviare una singola voce nel percorso. |
| **Errore** | Numero totale di errori che si sono verificati durante un percorso ma che non hanno impedito il corretto funzionamento del percorso. |
| **Errore in azione** | Numero totale di errori che si sono verificati per le azioni. |
| **Errore nell&#39;arricchimento** | Numero totale di errori che si sono verificati per un arricchimento dei dati durante la chiamata di un&#39;origine dati/gruppo di campi. |
| **Errore nell&#39;evento** | Numero totale di errori verificatisi per gli eventi. |
| **Frequenza errori** | Numero totale di errori che si sono verificati durante un percorso rispetto al numero totale di occorrenze nel percorso. |
| **Azione eseguita** | Numero totale di azioni eseguite per un percorso. |
| **Arricchimento eseguito** | Numero totale di arricchimenti eseguiti richiamando un’origine dati per ottenere gruppi di campi specifici. |
| **Evento eseguito** | Numero totale di azioni eseguite per un percorso. |
| **Orchestrazione eseguita** | Numero totale di oggetti orchestrazione (fine, attesa, condizione) eseguiti per un percorso. |
| **Non riuscito** | Numero totale di percorsi non eseguiti correttamente. |
| **Frequenza non riuscita** | Numero totale di percorsi che non sono stati eseguiti correttamente rispetto al numero di percorsi di esecuzione. |

## Metriche di consegna {#delivery-metrics}

La tabella seguente fornisce l’elenco delle metriche utilizzate nei rapporti sui percorsi, le relative definizioni e formule.

| Metrica | Definizione |
|--- |--- |
| **elenco Bloccati** | Numero di destinatari che hanno dichiarato un’e-mail come spam o posta indesiderata. |
| **Tasso di Elenco Bloccati** | Numero totale di messaggi in inserire nell&#39;elenco Bloccati rispetto ai messaggi inviati. |
| **Rimbalzi + errori** | Totale degli errori cumulati durante la consegna e l’elaborazione automatica della restituzione in relazione al numero totale di messaggi inviati. |
| **Rimbalzo + tasso di errore** | Numero totale di messaggi rimbalzati rispetto ai messaggi inviati. |
| **Click** | Numero di volte in cui è stato fatto clic su un contenuto in una consegna. |
| **Frequenza di click-through** | Numero totale di clic in una consegna rispetto al numero di messaggi inviati. |
| **Consegnate** | Numero di messaggi inviati correttamente in relazione al numero totale di messaggi inviati. |
| **Tasso di consegna** | Numero totale di messaggi consegnati correttamente rispetto ai messaggi inviati. |
| **Errore** | Numero totale di errori che si sono verificati durante un percorso ma che non hanno impedito il corretto funzionamento del percorso. |
| **Rimbalzo duro** | Numero totale di errori permanenti, ad esempio un indirizzo e-mail errato. |
| **Frequenza di rimbalzo difficile** | Numero totale di consegne non riuscite a causa di errori permanenti rispetto ai messaggi inviati. |
| **Pagina speculare** | Numero di destinatari che hanno fatto clic sul collegamento della pagina speculare. |
| **Frequenza pagina speculare** | Numero totale di clic sul collegamento della pagina speculare rispetto al totale dei messaggi consegnati. |
| **Open** | Numero di volte in cui un messaggio è stato aperto in una consegna. |
| **Open Rate** | Numero totale di messaggi aperti rispetto al numero di messaggi inviati. |
| **Quarantena** | Numero di messaggi rimbalzati e risultati nella quarantena dell’indirizzo. |
| **Tasso di quarantena** | Numero totale di quarantene rispetto ai messaggi inviati. |
| **Rifiutato** | Numero di messaggi classificati come spam dai server SMTP. |
| **Tasso rifiutato** | Numero totale di messaggi contrassegnati come rifiutati rispetto ai messaggi inviati. |
| **Elaborato/inviato** | Numero totale di invii per la consegna. |
| **Rimbalzo morbido** | Numero totale di errori temporanei, ad esempio una casella in entrata completa. |
| **Frequenza di rimbalzo morbida** | Numero totale di consegne non riuscite a causa di motivi temporanei rispetto ai messaggi inviati. |
| **Clic univoco** | Numero di destinatari che hanno fatto clic su un contenuto in una consegna. |
| **Aperture univoche** | Numero di destinatari che hanno aperto la consegna. |
| **Annulla sottoscrizione** | Numero di clic sul collegamento di annullamento dell’abbonamento. |
| **Tasso di annullamento sottoscrizione** | Numero totale di annullamenti di abbonamenti per destinatario rispetto ai messaggi consegnati. |
