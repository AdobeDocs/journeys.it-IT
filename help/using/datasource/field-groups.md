---
product: adobe campaign
title: Gruppi di campi
description: Informazioni sui gruppi di campi
feature: Journeys
role: User
level: Intermediate
exl-id: 6f7f2673-9080-4274-afa3-a0255798f78d
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# Gruppi di campi {#concept_ntl_ypt_52b}

I gruppi di campi sono insiemi di campi che è possibile recuperare da un’origine dati e utilizzare in un percorso.

## Definizione dei gruppi di campi {#section_dsz_kjd_fjb}

Per ogni origine dati puoi definire diversi gruppi di campi.

Ad esempio, puoi creare un gruppo di campi con il numero di telefono, l’e-mail, il nome e l’indirizzo del profilo. Potrai quindi utilizzare questi dati nel tuo percorso per creare condizioni. Ad esempio, puoi decidere di inviare un SMS solo se il numero di telefono del profilo non è vuoto. Se è vuoto, puoi inviare un’e-mail.

Anche se viene aggiunto automaticamente un nome predefinito, ti consigliamo di assegnare un nome al gruppo di campi. In effetti, il nome del gruppo di campi sarà visibile agli altri utenti in [!DNL Journey Orchestration]. È consigliabile assegnare un nome pertinente ai gruppi di campi.

Quando un campo origine dati viene utilizzato in un percorso, il sistema recupererà tutti i campi definiti per quel gruppo di campi. Pertanto, è consigliabile selezionare solo i campi necessari per i percorsi. Questo ridurrà la latenza della richiesta nei percorsi aumentando così le prestazioni. È possibile aggiungere facilmente più campi nei gruppi di campi in un secondo momento.

Il numero di percorsi che utilizzano un gruppo di campi viene visualizzato nella **[!UICONTROL Used in]** campo . Puoi fare clic su **[!UICONTROL View journeys]** per visualizzare l’elenco dei percorsi che utilizzano questo gruppo di campi.

>[!NOTE]
>
>Tieni presente che se un gruppo di campi non ha un campo, non verrà visualizzato nell’editor espressioni.

![](../assets/journey3bis.png)

## Ciclo di vita del gruppo di campi {#section_abk_njd_fjb}

È possibile aggiungere o rimuovere campi da un gruppo di campi non utilizzato in alcuna bozza o in un percorso live.

Puoi aggiungere ma non rimuovere un campo da un gruppo di campi utilizzato in uno o più percorsi di bozza o live. In questo modo si evitano percorsi di rottura.

Per eliminare un campo da un gruppo di campi utilizzato in uno o più percorsi, procedere come segue. Utilizziamo un esempio di gruppo di campi denominato &quot;Gruppo di campi A&quot;.

1. Nell’elenco dei gruppi di campi, posiziona il cursore su &quot;Gruppo di campi A&quot; e fai clic sul pulsante **[!UICONTROL Duplicate]** a destra. Ad esempio, denominare il gruppo di campi duplicato &quot;Gruppo di campi B&quot;.
1. In &quot;Gruppo di campi B&quot;, rimuovere i campi che non si desidera più.
1. In &quot;Gruppo di campi A&quot;, controlla dove viene utilizzato questo gruppo di campi. Queste informazioni vengono visualizzate nel **[!UICONTROL Used in]** campo .
1. Aprire tutti i percorsi che utilizzano &quot;Gruppo di campi A&quot;.
1. Crea nuove versioni di ciascuno di questi percorsi. Modifica tutte le attività utilizzando &quot;Gruppo di campi A&quot; e seleziona &quot;Gruppo di campi B&quot;.
1. Arrestare le vecchie versioni di percorsi che utilizzano &quot;Gruppo di campi A&quot;. Non dovrebbe quindi essere presente alcun percorso che utilizzi &quot;Gruppo di campi A&quot;.
1. Rimuovere il &quot;Gruppo di campi A&quot; in quanto non è più utilizzato.
