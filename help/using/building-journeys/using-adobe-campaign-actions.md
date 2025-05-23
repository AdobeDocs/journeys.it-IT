---
product: adobe campaign
title: Utilizzo delle azioni di Adobe Campaign
description: Scopri le azioni di Adobe Campaign
feature: Journeys
role: User
level: Intermediate
exl-id: b2e5c333-d0d8-4fe1-a6b8-5f2e6b3624a4
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 2%

---

# Utilizzo di Adobe Campaign Standard {#using_campaign_action}


>[!CAUTION]
>
>**Ricerca di Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._



Se disponi di Adobe Campaign Standard, sono disponibili le seguenti attività di azioni predefinite: **[!UICONTROL Email]**, **[!UICONTROL Push]** e **[!UICONTROL SMS]**.

>[!NOTE]
>
>A questo scopo, devi configurare l’azione incorporata. Consulta [questa pagina](../action/working-with-adobe-campaign.md).

Per ciascuno di questi canali, seleziona un **modello** di Adobe Campaign Standard Transactional Messaging. [!DNL Journey Orchestration] non è una soluzione per l&#39;invio di messaggi. Per i canali e-mail, SMS e push incorporati, ci affidiamo alla messaggistica transazionale per eseguire l’invio dei messaggi. Ciò significa che se desideri utilizzare un determinato modello di messaggio nei tuoi percorsi, devi pubblicarlo in Adobe Campaign Standard. Per informazioni su come utilizzare questa funzione, consulta [questa pagina](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=it).

>[!NOTE]
>
>Per poter essere utilizzato in Journey Orchestration, il messaggio transazionale di Campaign Standard e il relativo evento associato devono essere pubblicati. Se l’evento viene pubblicato ma il messaggio non lo è, non sarà visibile nell’interfaccia di Journey Orchestration. Se il messaggio viene pubblicato ma il relativo evento associato non lo è, sarà visibile nell’interfaccia di Journey Orchestration ma non sarà utilizzabile.

![](../assets/journey59.png)

Puoi utilizzare un evento (noto anche come modello di messaggistica transazionale di profilo in tempo reale).

>[!NOTE]
>
>Quando inviamo messaggi transazionali in tempo reale (rtEvent) o quando inviamo messaggi con un sistema di terze parti grazie a un’azione personalizzata, è necessaria una configurazione specifica per la gestione dell’affaticamento, dell’elenco Bloccati o dell’annullamento dell’abbonamento. Ad esempio, se un attributo &quot;unsubscribe&quot; è memorizzato in Adobe Experience Platform o in un sistema di terze parti, sarà necessario aggiungere una condizione prima dell’invio del messaggio per verificare questa condizione.

Quando selezioni un modello, tutti i campi previsti nel payload del messaggio vengono visualizzati nel riquadro di configurazione dell&#39;attività in **[!UICONTROL Address]** e **[!UICONTROL Personalization Data]**. Devi mappare ciascuno di questi campi con il campo che desideri utilizzare, dall’evento o dall’origine dati. È inoltre possibile utilizzare l’editor di espressioni avanzate per passare manualmente un valore, manipolare i dati sulle informazioni recuperate (ad esempio, convertire una stringa in maiuscolo) o utilizzare funzioni quali &quot;if, then, else&quot;. Consulta [questa pagina](../expression/expressionadvanced.md).

![](../assets/journey60.png)

## E-mail e SMS {#section_asc_51g_nhb}

Per **[!UICONTROL Email]** e **[!UICONTROL SMS]**, i parametri sono identici.

>[!NOTE]
>
>Per le e-mail, se utilizzi un modello transazionale di profili, il meccanismo di annullamento dell’abbonamento viene gestito da Campaign Standard come preconfigurato. È sufficiente aggiungere un blocco di contenuto **[!UICONTROL Unsubscription link]** nel modello ([ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=it)). Se utilizzi un modello basato su eventi (rtEvent), devi aggiungere nel messaggio un collegamento che trasmette l’e-mail della persona nel parametro URL e che punta a una pagina di destinazione per l’annullamento dell’abbonamento. Devi creare questa pagina di destinazione e assicurarti che la decisione della persona di annullare l’abbonamento sia trasmessa ad Adobe.

Innanzitutto, devi scegliere un modello di messaggistica transazionale. Consulta [questa pagina](../building-journeys/about-action-activities.md).

Sono disponibili due categorie: **[!UICONTROL Address]** e **[!UICONTROL Personalization Data]**.

È possibile definire facilmente dove recuperare **[!UICONTROL Address]** o **[!UICONTROL Personalization Data]** utilizzando l&#39;interfaccia. Puoi sfogliare gli eventi e i campi dell’origine dati disponibili. È inoltre possibile utilizzare l’editor di espressioni avanzate per casi di utilizzo più avanzati, ad esempio per utilizzare un’origine dati che richiede il passaggio di parametri o l’esecuzione di manipolazioni. Consulta [questa pagina](../expression/expressionadvanced.md).

**[!UICONTROL Address]**

>[!NOTE]
>
>Questa categoria è visibile solo se selezioni un messaggio transazionale &quot;evento&quot;. Per i messaggi &quot;profile&quot;, il campo **[!UICONTROL Address]** viene recuperato automaticamente da Adobe Campaign Standard.

Questi sono i campi necessari per sapere dove inviare il messaggio. Per un modello e-mail, si tratta dell’indirizzo e-mail. Per un SMS, è il numero del cellulare.

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Non è possibile trasmettere una raccolta nei dati di personalizzazione. Se l’e-mail o l’SMS transazionale prevede delle raccolte, non funzioneranno. Inoltre, i dati di personalizzazione hanno un formato previsto (ad esempio, stringa, decimale e così via). Devi fare attenzione a rispettare questi formati previsti.

Questi sono i campi previsti dal messaggio di Adobe Campaign Standard. Questi campi possono essere utilizzati per personalizzare il messaggio, applicare la formattazione condizionale o scegliere una variante di messaggio specifica.

![](../assets/journey62.png)

## Push {#section_im3_hvf_nhb}

Prima di utilizzare l’attività push, è necessario configurare l’app mobile e Campaign Standard per inviare le notifiche push. Utilizza questo [articolo](https://helpx.adobe.com/it/campaign/kb/integrate-mobile-sdk.html) per eseguire i passaggi di implementazione necessari per Mobile.

Innanzitutto, devi scegliere un’app mobile dall’elenco a discesa e un messaggio transazionale. Consulta [questa pagina](../building-journeys/about-action-activities.md).

![](../assets/journey62bis.png)

Sono disponibili due categorie: **[!UICONTROL Target]** e **[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>Questa categoria è visibile solo se selezioni un messaggio evento. Per i messaggi di profilo, i campi **[!UICONTROL Target]** vengono recuperati automaticamente dal sistema utilizzando la riconciliazione eseguita da Adobe Campaign Standard.

In questa sezione è necessario definire **[!UICONTROL Push platform]**. L&#39;elenco a discesa consente di selezionare **[!UICONTROL Apple Push Notification Server]** (iOS) o **[!UICONTROL Firebase Cloud Messaging]** (Android). In alternativa, puoi selezionare un campo specifico da un evento o da un’origine dati oppure definire un’espressione avanzata.

È inoltre necessario definire **[!UICONTROL Registration Token]**. L&#39;espressione dipende dalla modalità di definizione del token nel payload dell&#39;evento o in altre informazioni di [!DNL Journey Orchestration]. Può essere un campo semplice o un’espressione più complessa, nel caso in cui il token sia definito in una raccolta, ad esempio:

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Non è possibile trasmettere una raccolta nei dati di personalizzazione. Se il push transazionale prevede delle raccolte, non funzionerà. Inoltre, i dati di personalizzazione hanno un formato previsto (ad esempio, stringa, decimale e così via). Devi fare attenzione a rispettare questi formati previsti.

Questi sono i campi previsti dal modello transazionale utilizzato nel messaggio di Adobe Campaign Standard. Questi campi possono essere utilizzati per personalizzare il messaggio, applicare la formattazione condizionale o scegliere una variante di messaggio specifica.
