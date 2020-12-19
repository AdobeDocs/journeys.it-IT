---
product: adobe campaign
solution: Journey Orchestration
title: Informazioni sulle attività azione
description: Informazioni sulle attività di azione
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Informazioni sulle attività azione {#concept_hbj_hrt_52b}

Dalla palette, sul lato sinistro dello schermo, sotto **[!UICONTROL Events]** e **[!UICONTROL Orchestration]**, si trova la categoria **[!UICONTROL Actions]**.

![](../assets/journey58.png)

Queste attività rappresentano i diversi canali di comunicazione disponibili. Potete combinarle per creare uno scenario multicanale.

Se  Adobe Campaign Standard, sono disponibili le seguenti attività pronte all’uso: **[!UICONTROL Email]**, **[!UICONTROL Push]** e **[!UICONTROL SMS]**. Consulta [questa pagina](../building-journeys/using-adobe-campaign-actions.md).

Se hai configurato azioni personalizzate, queste verranno visualizzate anche qui (vedere [questa pagina](../building-journeys/using-custom-actions.md)).

Quando rilasci un&#39;attività di azione nell&#39;area di lavoro, puoi definire un **[!UICONTROL Label]**. Questo consente di aggiungere un suffisso al nome dell’azione che verrà visualizzato sotto l’attività nell’area di lavoro. Questa funzione è utile se durante il viaggio utilizzate più volte la stessa azione e desiderate identificarla più facilmente. Anche i rapporti saranno più facili da leggere. È inoltre possibile aggiungere un **[!UICONTROL Description]** facoltativo.

![](../assets/journey59bis.png)

Quando si verifica un errore in un’azione o in una condizione, il percorso di un singolo utente si arresta. L’unico modo per far sì che continui è selezionare la casella **[!UICONTROL Add an alternative path in case of a timeout or an error]** (Aggiungi percorso alternativo in caso di errore o timeout). Vedi [questa sezione](../building-journeys/using-the-journey-designer.md#paths).
