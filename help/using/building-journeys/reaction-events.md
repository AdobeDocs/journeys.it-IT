---
title: Eventi di reazione
description: Informazioni sugli eventi di reazione
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
source-git-commit: 2b44cd9db7732c5e272b69e2583a5f81b4580d11
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Eventi di reazione {#section_dhx_gss_dgb}

Tra le diverse attività dell&#39;evento disponibili nella palette, l&#39; **[!UICONTROL Reactions]** evento incorporato è disponibile. Questa attività consente di reagire ai dati di tracciamento relativi a un messaggio inviato con e-mail, SMS o attività push nello stesso percorso. Queste informazioni provengono dai messaggi transazionali  Adobe Campaign Standard. Queste informazioni vengono acquisite in tempo reale nel momento in cui vengono condivise con l&#39;Adobe Experience Platform. Per le notifiche push, puoi reagire ai messaggi su cui hai fatto clic, che sono stati inviati o che hanno avuto esito negativo. Per gli SMS, è possibile reagire ai messaggi inviati o non riusciti. Per le e-mail, potete reagire ai messaggi su cui è stato fatto clic, che sono stati inviati, che sono stati aperti o che hanno avuto esito negativo.

È inoltre possibile utilizzare questo meccanismo per eseguire un&#39;azione in assenza di reazioni ai messaggi. A tal fine, create un secondo percorso parallelo all&#39;attività di reazione e aggiungete un&#39;attività di attesa. Se durante il periodo definito nell&#39;attività di attesa non è presente alcuna reazione, verrà scelto il secondo percorso. Potete scegliere di inviare, ad esempio, un messaggio di follow-up.

È possibile utilizzare un&#39;attività di reazione nel quadro solo se è già presente un&#39;attività e-mail, push o SMS.

See [About action activities](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Di seguito sono riportati i diversi passaggi per configurare gli eventi di reazione:

1. Aggiungete una **[!UICONTROL Label]** alla reazione. Questo passaggio è facoltativo.
1. Dall&#39;elenco a discesa, selezionate l&#39;attività di azione a cui desiderate reagire. È possibile selezionare qualsiasi attività di azione posizionata nei passaggi precedenti del percorso.
1. A seconda dell’azione selezionata (e-mail, SMS o notifica push), scegliete a cosa rispondere.
1. È possibile definire una condizione come passaggio facoltativo. Ad esempio, dopo un’azione e-mail, potete decidere di creare due percorsi, uno con un evento di reazione per monitorare i clic solo per VIP clienti e uno con un evento di reazione per monitorare i clic eseguiti dalle donne.

>[!NOTE]
>
>Gli eventi di reazione funzionano con  Adobe Campaign Standard, sia che sia distribuito sui server AWS o Azure.
>
>Gli eventi di reazione non possono tenere traccia delle azioni e-mail, SMS o push che avvengono in un percorso diverso.
>
>Gli eventi di reazione tengono traccia dei clic sui collegamenti di tipo &quot;tracciati&quot; (vedere questa [pagina](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Non vengono presi in considerazione i collegamenti di annullamento sottoscrizione e di pagina mirror.

>[!IMPORTANT]
>
>I client e-mail come Gmail consentono il blocco delle immagini. Le aperture e-mail vengono tracciate utilizzando un’immagine di 0 pixel inclusa nel messaggio e-mail. Se le immagini sono bloccate, le aperture e-mail non verranno prese in considerazione.
