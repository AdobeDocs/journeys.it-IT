---
product: adobe campaign
title: Gestione del fuso orario
description: Informazioni sulla gestione del fuso orario
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 77fcc4ba02a855d4d584627625a08abb4af0da2f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 2%

---

# Gestione del fuso orario {#timezone_management}

È possibile definire un fuso orario nel [proprietà](../building-journeys/changing-properties.md) del tuo percorso.

Per accedere a Proprietà, fai clic sull’icona della matita in alto a destra dello schermo.

Questo fuso orario verrà utilizzato per ogni attività del percorso contenente un elemento temporale come:

* [Condizione temporale](../building-journeys/condition-activity.md#time_condition)
* [Condizione data](../building-journeys/condition-activity.md#date_condition)
* [Attesa personalizzata](../building-journeys/wait-activity.md#custom)

Puoi selezionare un fuso orario o scegliere di utilizzare quello definito nel profilo utente.

>[!NOTE]
>
>Il fuso orario del profilo funziona con **fuso orario** campo esistente nel **Dettagli sulle preferenze** gruppo di campi.

## Definizione di un fuso orario fisso {#fixed-timezone}

È inoltre possibile correggere il fuso orario. Cancella il fuso orario predefinito e selezionane uno dall’elenco a discesa. Se si utilizza un fuso orario fisso, questo sarà lo stesso per tutte le persone che entrano nel percorso.

A tale scopo, in **[!UICONTROL Properties]**, seleziona un fuso orario.

![](../assets/journey72.png)

## Utilizzo dei profili per definire il fuso orario del percorso {#timezone-from-profiles}

Se l’evento di ingresso del percorso ha uno spazio dei nomi, il che significa che il percorso può raggiungere il servizio Profilo cliente in tempo reale di Adobe Experience Platform, puoi utilizzare il fuso orario definito a livello di profilo. A tale scopo, in **Proprietà**, spunta **Utilizza il fuso orario del profilo in attese e condizioni**. Questa opzione non è selezionata per impostazione predefinita.

Se per un profilo è stato definito un fuso orario, questo verrà recuperato e utilizzato dal percorso. In caso contrario, il fuso orario utilizzato sarà quello definito nel campo del fuso orario.

![](../assets/journey73.png)

## Utilizzo dei fusi orari nelle espressioni {#timezone-in-expressions}

Le date di inizio e di fine di un percorso non possono essere collegate a un fuso orario specifico. Vengono associate automaticamente al fuso orario dell’istanza.
