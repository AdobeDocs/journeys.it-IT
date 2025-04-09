---
product: adobe campaign
title: Modifica delle proprietà
description: Scopri come modificare le proprietà
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 2%

---

# Modifica delle proprietà {#concept_prq_wqt_52b}



>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


Fai clic sull’icona della matita, in alto a destra per accedere alle proprietà del percorso.

Puoi modificare il nome del percorso, aggiungere una descrizione, consentire il rientro, scegliere le date di inizio e di fine e definire una durata di **[!UICONTROL Timeout and error]** se sei un amministratore.

Per i percorsi live, questa schermata mostra la data di pubblicazione e il nome dell’utente che ha pubblicato il percorso.

**Copia dettagli tecnici** consente di copiare informazioni tecniche sul percorso che il team di supporto può utilizzare per la risoluzione dei problemi. Vengono copiate le seguenti informazioni: JourneyVersion UID, OrgID, orgName, sandboxName, lastDeployedBy, lastDeployedAt.

![](../assets/journey32.png)

## Ingresso{#entrance}

Per impostazione predefinita, i nuovi percorsi consentono il reingresso. È possibile deselezionare l’opzione per i percorsi &quot;one shot&quot; (una sola volta), ad esempio se si desidera offrire un regalo una tantum quando una persona entra in un negozio. In tal caso, non vuoi che il cliente possa reinserire il percorso e ricevere nuovamente l’offerta.

Quando un percorso &quot;termina&quot;, avrà lo stato **[!UICONTROL Closed (no entrance)]**. Il percorso smetterà di far entrare nel percorso nuovi individui. Le persone già nel percorso finiranno normalmente il percorso.

Dopo il timeout globale predefinito di 30 giorni, il percorso passerà allo stato **Completato**. Consulta questa [sezione](#global_timeout).

## Timeout ed errore nelle attività del percorso {#timeout_and_error}

Quando modifichi un’attività di azione o condizione, puoi definire un percorso alternativo in caso di errore o timeout. Se l&#39;elaborazione dell&#39;attività di interrogazione di un sistema di terze parti supera la durata di timeout definita nel campo delle proprietà del percorso (**[!UICONTROL Timeout and  error]**), verrà scelto il secondo percorso per eseguire una potenziale azione di fallback.

I valori autorizzati sono compresi tra 1 e 30 secondi.

È consigliabile definire un valore di **[!UICONTROL Timeout and error]** molto breve se il percorso è sensibile all&#39;ora (ad esempio, per reagire alla posizione in tempo reale di una persona) perché non è possibile ritardare l&#39;azione per più di alcuni secondi. Se il percorso è meno sensibile al tempo, è possibile utilizzare un valore più lungo per dare più tempo al sistema chiamato per inviare una risposta valida.

[!DNL Journey Orchestration] utilizza anche un timeout globale. Consulta la [sezione successiva](#global_timeout).

## Timeout percorso globale {#global_timeout}

Oltre al [timeout](#timeout_and_error) utilizzato nelle attività di percorso, esiste anche un timeout di percorso globale che non viene visualizzato nell&#39;interfaccia e non può essere modificato. Questo timeout interromperà l’avanzamento delle persone nel percorso 30 giorni dopo l’ingresso. Ciò significa che la durata del percorso di un individuo non può superare i 30 giorni. Dopo il periodo di timeout di 30 giorni, i dati dell’individuo vengono eliminati. Gli individui che ancora scorrono nel percorso alla fine del periodo di timeout verranno interrotti e verranno presi in considerazione come errori nella generazione dei rapporti.

>[!NOTE]
>
>[!DNL Journey Orchestration] non reagisce direttamente alle richieste di rinuncia alla privacy, di accesso o di eliminazione. Tuttavia, il timeout globale assicura che gli individui non rimangano mai più di 30 giorni in qualsiasi percorso.

A causa del timeout di 30 percorsi, quando il rientro del percorso non è consentito, non possiamo assicurarci che il blocco del rientro funzioni per più di 30 giorni. Infatti, poiché si eliminano tutte le informazioni sulle persone che sono entrate nel percorso 30 giorni dopo il loro ingresso, non è possibile conoscere la persona che è entrata in precedenza, più di 30 giorni fa.

## Fuso orario e fuso orario del profilo {#timezone}

Il fuso orario è definito a livello di percorso.

Puoi immettere un fuso orario fisso o utilizzare i profili Adobe Experience Platform per definire il fuso orario del percorso.

Per ulteriori informazioni sulla gestione del fuso orario, vedere [questa pagina](../building-journeys/timezone-management.md).
