---
product: adobe campaign
title: Gestione del fuso orario
description: Informazioni sulla gestione del fuso orario
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 8%

---

# Gestione del fuso orario {#timezone_management}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._



Puoi definire un fuso orario nelle [proprietà](../building-journeys/changing-properties.md) del tuo percorso.

Per accedere a Proprietà, fai clic sull’icona della matita in alto a destra dello schermo.

Questo fuso orario verrà utilizzato per ogni attività del percorso contenente un elemento temporale come:

* [Condizione temporale](../building-journeys/condition-activity.md#time_condition)
* [Condizione data](../building-journeys/condition-activity.md#date_condition)
* [Attesa personalizzata](../building-journeys/wait-activity.md#custom)

Puoi selezionare un fuso orario o scegliere di utilizzare quello definito nel profilo utente.

>[!NOTE]
>
>Il fuso orario del profilo funziona con il campo **fuso orario** esistente nel gruppo di campi **Dettagli preferenza**.

## Definizione di un fuso orario fisso {#fixed-timezone}

È inoltre possibile correggere il fuso orario. Cancella il fuso orario predefinito e selezionane uno dall’elenco a discesa. Se si utilizza un fuso orario fisso, questo sarà lo stesso per tutte le persone che entrano nel percorso.

A tale scopo, in **[!UICONTROL Properties]**, selezionare un fuso orario.

![](../assets/journey72.png)

## Utilizzo dei profili per definire il fuso orario del percorso {#timezone-from-profiles}

Se l’evento di ingresso del percorso ha uno spazio dei nomi, il che significa che il percorso può raggiungere il servizio Profilo cliente in tempo reale di Adobe Experience Platform, puoi utilizzare il fuso orario definito a livello di profilo. A tale scopo, in **Proprietà**, selezionare **Usa fuso orario profilo in attese e condizioni**. Questa opzione non è selezionata per impostazione predefinita.

Se per un profilo è stato definito un fuso orario, questo verrà recuperato e utilizzato dal percorso. In caso contrario, il fuso orario utilizzato sarà quello definito nel campo del fuso orario.

![](../assets/journey73.png)

## Utilizzo dei fusi orari nelle espressioni {#timezone-in-expressions}

Le date di inizio e di fine di un percorso non possono essere collegate a un fuso orario specifico. Vengono associate automaticamente al fuso orario dell’istanza.
