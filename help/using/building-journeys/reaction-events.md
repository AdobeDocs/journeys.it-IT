---
product: adobe campaign
solution: Journey Orchestration
title: Eventi di reazione
description: Scopri gli eventi di reazione
feature: Percorsi
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 1%

---


# Eventi di reazione {#section_dhx_gss_dgb}

Tra le diverse attività dell’evento disponibili nella palette, puoi trovare l’evento incorporato **[!UICONTROL Reactions]** . Questa attività ti consente di reagire ai dati di tracciamento relativi a un messaggio inviato con attività e-mail, SMS o push nello stesso percorso. Queste informazioni provengono dalla messaggistica transazionale in Adobe Campaign Standard. Acquisiamo queste informazioni in tempo reale nel momento in cui vengono condivise con Adobe Experience Platform. Per le notifiche push, puoi reagire ai messaggi con clic, inviati o non riusciti. Per i messaggi SMS, puoi reagire ai messaggi inviati o non riusciti. Per le e-mail puoi reagire a messaggi con un clic, con un clic, un invio, un messaggio aperto o con errore.

Puoi inoltre utilizzare questo meccanismo per eseguire un’azione quando non vi sono reazioni ai messaggi. A questo scopo, crea un secondo percorso parallelo all’attività di reazione e aggiungi un’attività di attesa. Se non vi è alcuna reazione durante il periodo definito nell’attività di attesa, verrà scelto il secondo percorso. Puoi scegliere di inviare, ad esempio, un messaggio di follow-up.

Tieni presente che puoi utilizzare un’attività di reazione nell’area di lavoro solo se in precedenza è presente un’attività e-mail, push o SMS.

Consulta [Informazioni sulle attività di azione](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Di seguito sono riportati i diversi passaggi per configurare gli eventi di reazione:

1. Aggiungi un **[!UICONTROL Label]** alla reazione. Questo passaggio è facoltativo.
1. Dall’elenco a discesa, seleziona l’attività di azione a cui desideri reagire. Puoi selezionare qualsiasi attività di azione posizionata nei passaggi precedenti del percorso.
1. A seconda dell’azione selezionata (e-mail, SMS o notifica push), scegli a cosa vuoi reagire.
1. È possibile definire una condizione come passaggio facoltativo. Ad esempio, dopo un’azione e-mail, puoi decidere di creare due percorsi, uno con un evento di reazione per tracciare i clic solo per i clienti VIP e uno con un evento di reazione per tracciare i clic eseguiti dalle donne.

>[!NOTE]
>
>Gli eventi di reazione funzionano con Adobe Campaign Standard, sia che siano distribuiti su server AWS o Azure.
>
>Gli eventi di reazione non possono tenere traccia delle azioni e-mail, SMS o push che si verificano in un percorso diverso.
>
>Gli eventi di reazione tengono traccia dei clic sui collegamenti del tipo &quot;tracciato&quot; (consulta questa [pagina](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). I collegamenti di annullamento all’abbonamento e alle pagine mirror non vengono presi in considerazione.

>[!IMPORTANT]
>
>I client e-mail come Gmail consentono il blocco delle immagini. Le aperture delle e-mail vengono tracciate utilizzando un’immagine di 0 pixel inclusa nell’e-mail. Se le immagini sono bloccate, le aperture delle e-mail non verranno prese in considerazione.
