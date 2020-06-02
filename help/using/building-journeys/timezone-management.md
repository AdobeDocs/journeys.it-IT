---
title: Gestione del fuso orario
description: Informazioni sulla gestione del fuso orario
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
source-git-commit: 1ccf020a882c1d6d9bd00f2e9f5d6b2aee6f7829
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 2%

---



# Gestione del fuso orario {#timezone_management}

Puoi definire un fuso orario nelle [proprietà](../building-journeys/changing-properties.md) del tuo viaggio.

Per accedere a Proprietà, fai clic sull’icona matita in alto a destra nella schermata.

Questo fuso orario verrà utilizzato per ogni attività del viaggio contenente un elemento temporale come:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Potete selezionare un fuso orario o scegliere di utilizzare il fuso orario definito nel profilo utente.

## Definizione di un fuso orario fisso {#fixed-timezone}

È inoltre possibile fissare il fuso orario. Deselezionare il fuso orario predefinito e selezionarne uno dall&#39;elenco a discesa. Se utilizzate un fuso orario fisso, sarà lo stesso per tutti gli utenti che accedono al viaggio.

A tale scopo, in **[!UICONTROL Properties]**, selezionare un fuso orario.

![](../assets/journey73.png)

## Utilizzo di profili per definire il fuso orario di viaggio {#timezone-from-profiles}

Se l&#39;evento di ingresso del viaggio ha uno spazio dei nomi, il che significa che il viaggio può raggiungere il servizio di profilo cliente in tempo reale della piattaforma dati, il fuso orario è predefinito con quello specificato nel profilo del singolo che scorre nel viaggio.

Se un fuso orario è definito nel profilo di Experience Platform, può essere recuperato durante il viaggio.

Se il profilo del singolo non contiene un fuso orario, il fuso orario recuperato sarà quello definito nel campo del fuso orario.

A tal fine, **[!UICONTROL Properties]** verificare **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey72.png)

## Uso dei fusi orari nelle espressioni {#timezone-in-expressions}

Le date di inizio e di fine di un viaggio non possono essere collegate a un fuso orario specifico. Vengono automaticamente associati al fuso orario dell&#39;istanza.
