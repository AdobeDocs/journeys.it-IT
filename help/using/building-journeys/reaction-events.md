---
product: adobe campaign
title: Eventi di reazione
description: Scopri gli eventi di reazione
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 2%

---

# Eventi di reazione {#section_dhx_gss_dgb}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._



Tra le diverse attività evento disponibili nella palette, troverai l’evento predefinito **[!UICONTROL Reactions]**. Questa attività ti consente di reagire ai dati di tracciamento relativi a un messaggio inviato con attività e-mail, SMS o push all’interno dello stesso percorso. Queste informazioni provengono dalla messaggistica transazionale in Adobe Campaign Standard. Queste informazioni vengono acquisite in tempo reale nel momento in cui vengono condivise con Adobe Experience Platform. Per le notifiche push, puoi reagire ai messaggi con clic, inviati o non riusciti. Per i messaggi SMS, puoi reagire ai messaggi inviati o non riusciti. Per le e-mail, puoi reagire ai messaggi su cui hai fatto clic, che hai inviato, che hai aperto o non sei riuscito.

Puoi anche utilizzare questo meccanismo per eseguire un’azione quando non vi è alcuna reazione ai messaggi. A questo scopo, crea un secondo percorso parallelo all’attività di reazione e aggiungi un’attività Attendi. Se non si verifica alcuna reazione durante il periodo definito nell’attività Attendi, verrà scelto il secondo percorso. Puoi scegliere di inviare, ad esempio, un messaggio di follow-up.

Tieni presente che puoi utilizzare un’attività di reazione nell’area di lavoro solo se in precedenza era presente un’attività e-mail, push o SMS.

Consulta [Informazioni sulle attività di azione](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Di seguito sono riportati i diversi passaggi per configurare gli eventi di reazione:

1. Aggiungi **[!UICONTROL Label]** alla reazione. Questo passaggio è facoltativo.
1. Dall’elenco a discesa, seleziona l’attività di azione a cui desideri reagire. Puoi selezionare qualsiasi attività di azione posizionata nei passaggi precedenti del percorso.
1. A seconda dell’azione selezionata (e-mail, SMS o notifica push), scegli a cosa desideri reagire.
1. Puoi definire un timeout dell’evento (tra 40 secondi e 30 giorni) e un percorso di timeout. Questo creerà un secondo percorso per i singoli utenti che non hanno reagito entro la durata definita. Quando si esegue il test di un percorso che utilizza un evento di reazione, il valore predefinito e minimo della modalità di test **[!UICONTROL Wait time]** è di 40 secondi. Consulta [questa sezione](../building-journeys/testing-the-journey.md).

>[!NOTE]
>
>Gli eventi di reazione funzionano con Adobe Campaign Standard, sia che sia distribuito sui server di AWS che di Azure.
>
>Gli eventi di reazione non possono tenere traccia delle azioni e-mail, SMS o push che si verificano in un percorso diverso.
>
>Gli eventi di reazione tengono traccia dei clic sui collegamenti di tipo &quot;tracciato&quot; (vedi questa [pagina](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html?lang=it#about-tracked-urls)). L’annullamento dell’abbonamento e i collegamenti alle pagine mirror non vengono presi in considerazione.

>[!IMPORTANT]
>
>I client di posta elettronica come Gmail consentono il blocco delle immagini. Le aperture delle e-mail vengono tracciate utilizzando un’immagine a 0 pixel inclusa nell’e-mail. Se le immagini sono bloccate, le aperture delle e-mail non verranno prese in considerazione.
