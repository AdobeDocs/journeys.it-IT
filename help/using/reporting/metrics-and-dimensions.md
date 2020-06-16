---
title: Metriche e dimensioni
description: Informazioni su dimensioni e metriche disponibili per Journey Orchestration
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
source-git-commit: c6e7c27865eb34961f8901c9bde2c09527f67f15
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 0%

---


# Metriche e dimensioni {#concept_rfj_wpt_52b}

>[!NOTE]
>
>I dati di consegna verranno compilati solo se si dispone  Adobe Campaign Standard.

Qui puoi trovare l&#39;elenco di tutti i componenti disponibili nei report dinamici e le relative definizioni.

La tabella seguente riporta l’elenco delle dimensioni utilizzate nei rapporti sul viaggio e le relative definizioni.

Per ulteriori informazioni sulla compatibilità tra dimensioni e metriche, consulta [questa pagina](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Dimensioni del viaggio {#MBE_table_wk4_bnj_w2b}

Nella tabella seguente è riportato l’elenco delle dimensioni utilizzate nei rapporti sul percorso, le relative definizioni e formule.

| Dimensioni | Definizione |
|--- |--- |
| **Azione** | Elenco di tutte le azioni (nome **azione - etichetta** azione) utilizzate nei viaggi, ad esempio, Push - Conferma check out, E-mail - fedeltà premi. |
| **Origine dati** | Elenco delle origini dati (nome **origine** dati) utilizzate per arricchire i dati in un viaggio, ad esempio piattaforma esperienza, sistema di prenotazione. |
| **[!UICONTROL Event]** | Elenco di tutti gli eventi (nome **evento - etichetta** evento) utilizzati nei viaggi, ad esempio eventi Geometrixx - Check-Out Geometrixx. |
| **Gruppo di campi** | Elenco di gruppi di campi (nome **gruppo di** campi) utilizzati per arricchire i dati nei viaggi, ad esempio gruppo di campi Profilo, sistema di prenotazione Geometrixx. |
| **Viaggio** | Elenco di ogni viaggio (nome **del** viaggio) in modalità di prova e in diretta, ad esempio abbandono del carrello, notifica prenotazione alberghiera. |
| **Versione del viaggio** | Elenco di tutte le versioni pubblicate di un viaggio (nome del **viaggio + numero** della versione), ad esempio abbandono del carrello v1, notifica prenotazione alberghiera v2. |
| **Orchestrazione** | Elenco di tutte le attività di orchestrazione (**Condizione, Fine, Attesa**) definite e utilizzate nei viaggi. |

## Dimensioni di consegna {#delivery-dimensions}

La tabella seguente fornisce l’elenco delle dimensioni di consegna utilizzate nei rapporti di viaggio, le relative definizioni e formule.

| Dimensione | Definizione |
|--- |--- |
| **Browser** | Browser da cui è stato aperto il messaggio o su cui è stato fatto clic. |
| **Nome consegna** | Etichetta e ID della consegna. |
| **Dispositivo** | Dispositivo da cui è stata aperta/visualizzata/su cui è stato fatto clic la notifica e-mail/SMS/push. |
| **Tipo di messaggio** | Canale utilizzato per la consegna, ad esempio e-mail, SMS, notifica push o In-App. |
| **Nome app mobile** | Nome dell’applicazione mobile |
| **Platform** | Platform del dispositivo da cui è stato aperto/visualizzato/fatto clic sul messaggio. |
| **[!UICONTROL Push platform]** | Platform del dispositivo da cui è stata aperta la notifica push, ad esempio iOS o Android. |
| **Dominio destinatario** | Dominio utilizzato per aprire l’e-mail. |
| **URL tracciamento** | URL su cui l’utente ha fatto clic dal messaggio. |
| **Categoria URL tracciamento** | Categoria assegnata all’URL di tracciamento. |
| **Etichetta URL tracciamento** | Etichetta data all’URL, ad esempio pagina mirror, contattateci o aprite. |
| **Variante** | Variante del messaggio e-mail in caso di test A/B. |


## Metriche del viaggio {#MBE_p_p22_c4j_w2b}

La tabella seguente fornisce l’elenco delle metriche utilizzate nei report di viaggio, le relative definizioni e formule.

| Metrica | Definizione |
|--- |---|
| **Completato** | Numero totale di individui che hanno terminato normalmente il viaggio. |
| **Tasso di completamento** | Numero totale di persone che hanno terminato normalmente il viaggio rispetto al numero totale di persone che sono entrate nel viaggio. |
| **Corrente** | Numero totale di persone attualmente in viaggio, ossia quante persone sono entrate senza persone uscite, errori e timeout. |
| **Tasso corrente** | Numero totale di persone attualmente in viaggio rispetto al numero di persone che sono entrate nel viaggio. |
| **Inserito** | Numero totale di eventi che si sono verificati per avviare una singola voce nel viaggio. |
| **Errore** | Numero totale di errori che si sono verificati durante un viaggio ma che non hanno impedito il successo del viaggio. |
| **Errore in azione** | Numero totale di errori che si sono verificati per le azioni. |
| **Errore nell&#39;arricchimento** | Numero totale di errori che si sono verificati per un arricchimento dei dati durante la chiamata di un&#39;origine dati/gruppo di campi. |
| **Errore nell&#39;evento** | Numero totale di errori che si sono verificati per gli eventi. |
| **Frequenza errori** | Numero totale di errori che si sono verificati durante un viaggio rispetto al numero totale di occorrenze nel viaggio. |
| **Azione eseguita** | Numero totale di azioni eseguite per un viaggio. |
| **Arricchimento eseguito** | Numero totale di arricchimenti eseguiti chiamando un&#39;origine dati per ottenere gruppi di campi specifici. |
| **Evento di esecuzione** | Numero totale di azioni eseguite per un viaggio. |
| **Orchestrazione eseguita** | Numero totale di oggetti orchestrazione (fine, attesa, condizione) eseguiti per un viaggio. |
| **Operazione non riuscita** | Numero totale di viaggi che non sono stati eseguiti correttamente. |
| **Tasso di errore** | Numero totale di viaggi che non sono stati eseguiti correttamente rispetto al numero di percorsi di esecuzione. |

## Metriche di consegna {#delivery-metrics}

La tabella seguente fornisce l’elenco delle metriche utilizzate nei rapporti di viaggio, le relative definizioni e formule.

| Metrica | Definizione |
|--- |--- |
| **Elenco blocchi** | Numero di destinatari che hanno dichiarato un&#39;e-mail come spam o posta indesiderata. |
| **Frequenza elenco blocchi** | Numero totale di messaggi nell&#39;elenco blocchi rispetto ai messaggi inviati. |
| **Bounge + errori** | Totale degli errori cumulati durante l&#39;elaborazione del recapito e del ritorno automatico in relazione al numero totale di messaggi inviati. |
| **Rimbalzo + tasso di errore** | Numero totale di messaggi rimbalzati rispetto ai messaggi inviati. |
| **Clic** | Numero di volte in cui è stato fatto clic su un contenuto in una consegna. |
| **Tasso di click-through** | Numero totale di clic in una consegna rispetto al numero di messaggi inviati. |
| **Consegnato** | Numero di messaggi inviati correttamente, in relazione al numero totale di messaggi inviati. |
| **Tasso di consegna** | Numero totale di messaggi consegnati correttamente rispetto ai messaggi inviati. |
| **Errore** | Numero totale di errori che si sono verificati durante un viaggio ma che non hanno impedito il successo del viaggio. |
| **Rimbalzo duro** | Numero totale di errori permanenti, ad esempio un indirizzo e-mail errato. |
| **Velocità limite** | Numero totale di consegne non riuscite a causa di errori permanenti rispetto ai messaggi inviati. |
| **Mirror, pagina** | Numero di destinatari che hanno fatto clic sul collegamento della pagina mirror. |
| **Frequenza pagina speculare** | Numero totale di clic sul collegamento della pagina mirror rispetto al totale dei messaggi inviati. |
| **Apri** | Numero di volte in cui un messaggio è stato aperto in una consegna. |
| **Velocità di apertura** | Numero totale di messaggi aperti rispetto al numero di messaggi inviati. |
| **Quarantina** | Numero di messaggi rimbalzati e risultati nella quarantena dell&#39;indirizzo. |
| **Frequenza quarantena** | Numero totale di quarantena rispetto ai messaggi inviati. |
| **Rifiutato** | Numero di messaggi classificati come spam dai server SMTP. |
| **Tasso rifiutato** | Numero totale di messaggi contrassegnati come rifiutati rispetto ai messaggi inviati. |
| **Elaborato/inviato** | Numero totale di invii per la consegna. |
| **Soft bounce** | Numero totale di errori temporanei, ad esempio una casella in entrata completa. |
| **Frequenza rimbalzo morbida** | Numero totale di consegne non riuscite a causa di un motivo temporaneo rispetto ai messaggi inviati. |
| **Clic univoci** | Numero di destinatari che hanno fatto clic su un contenuto in una consegna. |
| **Aperture univoche** | Numero di destinatari che hanno aperto la consegna. |
| **Annulla sottoscrizione** | Numero di clic sul collegamento di annullamento della sottoscrizione. |
| **Tasso di annullamento sottoscrizione** | Numero totale di sottoscrizioni per destinatario rispetto ai messaggi consegnati. |
