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

I gruppi di campi sono insiemi di campi che è possibile recuperare da un&#39;origine dati e utilizzare in un percorso.

## Definizione dei gruppi di campi {#section_dsz_kjd_fjb}

Per ogni origine dati è possibile definire più gruppi di campi.

Ad esempio, puoi creare un gruppo di campi con il numero di telefono, l’e-mail, il nome e l’indirizzo del profilo. Potrai quindi utilizzare questi dati nel tuo percorso per creare condizioni. Ad esempio, puoi decidere di inviare un SMS solo se il numero di telefono del profilo non è vuoto. Se è vuoto, puoi inviare un’e-mail.

Anche se viene aggiunto automaticamente un nome predefinito, è consigliabile assegnare un nome al gruppo di campi. In effetti, il nome del gruppo di campi sarà visibile ad altri utenti in [!DNL Journey Orchestration]. Assegnare un nome pertinente ai gruppi di campi è una best practice.

Quando un campo origine dati viene utilizzato in un percorso, vengono recuperati tutti i campi definiti per tale gruppo di campi. Pertanto, è consigliabile selezionare solo i campi necessari per i percorsi. Questo ridurrà la latenza delle richieste nei percorsi, aumentando così le prestazioni. In seguito è possibile aggiungere facilmente altri campi nei gruppi di campi.

Il numero di percorsi che utilizzano un gruppo di campi viene visualizzato nel campo **[!UICONTROL Used in]**. È possibile fare clic sul pulsante **[!UICONTROL View journeys]** per visualizzare l&#39;elenco dei percorsi che utilizzano questo gruppo di campi.

>[!NOTE]
>
>Tieni presente che se un gruppo di campi non ha alcun campo, non verrà visualizzato nell’editor espressioni.

![](../assets/journey3bis.png)

## Ciclo di vita del gruppo di campi {#section_abk_njd_fjb}

Puoi aggiungere o rimuovere campi da un gruppo di campi che non è utilizzato in alcun percorso in bozza o live.

Puoi aggiungere ma non rimuovere un campo da un gruppo di campi utilizzato in uno o più percorsi in bozza o live. In questo modo si evitano percorsi.

Per eliminare un campo da un gruppo di campi utilizzato in uno o più percorsi, eseguire la procedura seguente. Utilizziamo un esempio di gruppo di campi denominato &quot;Gruppo di campi A&quot;.

1. Nell&#39;elenco dei gruppi di campi posizionare il cursore sul gruppo di campi A e fare clic sull&#39;icona **[!UICONTROL Duplicate]** a destra. Ad esempio, assegna al gruppo di campi duplicato il nome &quot;Gruppo di campi B&quot;.
1. In &quot;Gruppo di campi B&quot;, rimuovere i campi non più desiderati.
1. In &quot;Gruppo di campi A&quot;, verificare dove viene utilizzato questo gruppo di campi. Queste informazioni vengono visualizzate nel campo **[!UICONTROL Used in]**.
1. Aprire tutti i percorsi che utilizzano &quot;Gruppo di campi A&quot;.
1. Crea nuove versioni di ciascuno di questi percorsi. Modificare tutte le attività utilizzando &quot;Gruppo di campi A&quot; e selezionare &quot;Gruppo di campi B&quot;.
1. Interrompere le versioni precedenti dei percorsi che utilizzano &quot;Gruppo di campi A&quot;. In questo caso non dovrebbe esistere alcun percorso che utilizzi &quot;Gruppo di campi A&quot;.
1. Rimuovere il &quot;Gruppo di campi A&quot; perché non è più utilizzato.
