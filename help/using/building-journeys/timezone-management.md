---
product: adobe campaign
solution: Journey Orchestration
title: Gestione del fuso orario
description: Informazioni sulla gestione del fuso orario
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: a19493178652a7fc91b7b778c5cb47eda72cd877
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# Gestione del fuso orario {#timezone_management}

Puoi definire un fuso orario nelle [proprietà](../building-journeys/changing-properties.md) del percorso.

Per accedere a Proprietà, fai clic sull’icona della matita in alto a destra dello schermo.

Questo fuso orario verrà utilizzato per ogni attività del percorso contenente un elemento temporale come:

* [Condizione di tempo](../building-journeys/condition-activity.md#time_condition)
* [Condizione data](../building-journeys/condition-activity.md#date_condition)
* [Attesa personalizzata](../building-journeys/wait-activity.md#custom)
* [Attesa data fissa](../building-journeys/wait-activity.md#fixed_date)

Puoi selezionare un fuso orario o scegliere di utilizzarlo nel profilo utente.

## Definizione di un fuso orario fisso {#fixed-timezone}

È inoltre possibile correggere il fuso orario. Deseleziona il fuso orario predefinito e selezionane uno dall’elenco a discesa. Se utilizzi un fuso orario fisso, sarà lo stesso per tutti gli utenti che accedono al percorso.

A questo scopo, in **[!UICONTROL Properties]**, seleziona un fuso orario.

![](../assets/journey72.png)

## Utilizzo dei profili per definire il fuso orario percorso {#timezone-from-profiles}

Se l’evento di ingresso del percorso ha uno spazio dei nomi, ovvero il percorso può raggiungere il servizio Profilo cliente in tempo reale di Adobe Experience Platform, il fuso orario è predefinito con quello specificato nel profilo del singolo utente che scorre nel percorso.

Se un fuso orario è definito nel profilo Adobe Experience Platform, può essere recuperato nel percorso.

Se il profilo della persona non contiene un fuso orario, il fuso orario recuperato sarà quello definito nel campo relativo al fuso orario.

A tale scopo, in **[!UICONTROL Properties]**, selezionare **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey73.png)

## Uso dei fusi orari nelle espressioni {#timezone-in-expressions}

Le date di inizio e di fine di un percorso non possono essere collegate a un fuso orario specifico. Vengono automaticamente associati al fuso orario dell’istanza.
