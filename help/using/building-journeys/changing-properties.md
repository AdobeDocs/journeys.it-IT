---
product: adobe campaign
solution: Journey Orchestration
title: Modifica delle proprietà
description: Scopri come modificare le proprietà
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---



# Modifica delle proprietà {#concept_prq_wqt_52b}

Fai clic sull&#39;icona a forma di matita, in alto a destra per accedere alle proprietà del viaggio.

Potete cambiare il nome del viaggio, aggiungere una descrizione, consentire il rientro, scegliere le date di inizio e fine e definire una durata **[!UICONTROL Timeout and error]** se siete amministratori.

![](../assets/journey32.png)

## Entrata{#entrance}

Per impostazione predefinita, i nuovi viaggi consentono il rientro. Potete deselezionare l&#39;opzione per i viaggi &quot;una sola ripresa&quot;, ad esempio se desiderate offrire un regalo una tantum quando una persona entra in un negozio. In tal caso, non si desidera che il cliente possa rientrare nel percorso e ricevere nuovamente l&#39;offerta.

Quando un viaggio &quot;termina&quot;, avrà lo stato **[!UICONTROL Closed (no entrance)]**. Il viaggio smetterà di far entrare nuovi individui nel percorso. Le persone già in viaggio finiranno normalmente il viaggio.

## Timeout ed errore nelle attività di viaggio {#timeout_and_error}

Quando si modifica un&#39;azione o un&#39;attività di condizione, è possibile definire un percorso alternativo in caso di errore o timeout. Se l&#39;elaborazione dell&#39;attività che esegue l&#39;interrogazione a un sistema di terze parti supera la durata di timeout definita nel campo delle proprietà del viaggio (**[!UICONTROL Timeout and  error]**), verrà scelto il secondo percorso per eseguire una potenziale azione di fallback.

I valori autorizzati sono compresi tra 1 e 30 secondi.

È consigliabile definire un valore molto breve **[!UICONTROL Timeout and error]** se il viaggio è sensibile al tempo (ad esempio: reagire alla posizione in tempo reale di una persona) perché non è possibile ritardare l’azione per più di pochi secondi. Se il viaggio è meno sensibile al tempo, potete utilizzare un valore più lungo per dare più tempo al sistema chiamato per inviare una risposta valida.

[!DNL Journey Orchestration] utilizza anche un timeout globale. Vedere la sezione [successiva](#global_timeout).

## Timeout percorso globale {#global_timeout}

Oltre al [timeout](#timeout_and_error) utilizzato nelle attività di viaggio, esiste anche un timeout di viaggio globale che non viene visualizzato nell&#39;interfaccia e non può essere modificato. Questo timeout arresterà il progresso degli individui nel viaggio 30 giorni dopo il loro ingresso. Ciò significa che il viaggio di un individuo non può durare più di 30 giorni. Dopo il periodo di timeout di 30 giorni, i dati del singolo vengono eliminati. Gli individui che continuano a scorrere nel viaggio alla fine del periodo di timeout verranno interrotti e saranno presi in considerazione come errori nel reporting.

>[!NOTE]
>
>[!DNL Journey Orchestration] non risponde direttamente alle richieste di privacy opt-out, accesso o eliminazione. Tuttavia, il timeout globale assicura che gli utenti non restino mai più di 30 giorni in un qualsiasi viaggio.

A causa del timeout del viaggio di 30 giorni, quando il rientro del viaggio non è consentito, non possiamo assicurarci che il blocco del rientro funzioni più di 30 giorni. Infatti, mentre rimuoviamo tutte le informazioni sulle persone che sono entrate nel viaggio 30 giorni dopo il loro ingresso, non possiamo sapere che la persona è entrata in precedenza, più di 30 giorni fa.

## Fuso orario e fuso orario del profilo {#timezone}

Il fuso orario è definito a livello di viaggio.

Potete immettere un fuso orario fisso o utilizzare i profili Adobe Experience Platform per definire il fuso orario del viaggio.

Per ulteriori informazioni sulla gestione del fuso orario, vedere [questa pagina](../building-journeys/timezone-management.md).
