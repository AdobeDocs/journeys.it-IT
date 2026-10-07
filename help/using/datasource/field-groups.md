---
product: adobe campaign
title: Gruppi di campi
description: Informazioni sui gruppi di campi
feature: Journeys
role: User
level: Intermediate
exl-id: 6f7f2673-9080-4274-afa3-a0255798f78d
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 11%
---
# Gruppi di campi {#concept_ntl_ypt_52b}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._


I gruppi di campi sono insiemi di campi che è possibile recuperare da un&#39;origine dati e utilizzare in un percorso.

## Definizione dei gruppi di campi {#section_dsz_kjd_fjb}

Per ogni origine dati è possibile definire più gruppi di campi.

Ad esempio, puoi creare un gruppo di campi con il numero di telefono, l’e-mail, il nome e l’indirizzo del profilo. Potrai quindi utilizzare questi dati nel tuo percorso per creare condizioni. Ad esempio, puoi decidere di inviare un SMS solo se il numero di telefono del profilo non è vuoto. Se è vuoto, puoi inviare un’e-mail.

Anche se viene aggiunto automaticamente un nome predefinito, è consigliabile assegnare un nome al gruppo di campi. In effetti, il nome del gruppo di campi sarà visibile ad altri utenti in [!DNL Journey Orchestration]. Assegnare un nome pertinente ai gruppi di campi è una best practice.

Quando un campo origine dati viene utilizzato in un percorso, vengono recuperati tutti i campi definiti per tale gruppo di campi. Pertanto, è consigliabile selezionare solo i campi necessari per i percorsi. Questo ridurrà la latenza delle richieste nei percorsi, aumentando così le prestazioni. In seguito è possibile aggiungere facilmente altri campi nei gruppi di campi.

Il numero di percorsi che utilizzano un gruppo di campi viene visualizzato nel campo **[!UICONTROL Used in]**. È possibile fare clic sul pulsante **[!UICONTROL View journeys]** per visualizzare l&#39;elenco dei percorsi che utilizzano questo gruppo di campi.

>[!NOTE]
>
>Tieni presente che se un gruppo di campi non ha un campo, non verrà visualizzato nell’editor espressioni.

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
