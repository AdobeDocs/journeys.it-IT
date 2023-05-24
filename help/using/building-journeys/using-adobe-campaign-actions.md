---
product: adobe campaign
title: Utilizzo delle azioni di Adobe Campaign
description: Scopri le azioni di Adobe Campaign
feature: Journeys
role: User
level: Intermediate
exl-id: b2e5c333-d0d8-4fe1-a6b8-5f2e6b3624a4
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 5%

---

# Utilizzo di Adobe Campaign Standard {#using_campaign_action}

Se disponi di Adobe Campaign Standard, sono disponibili le seguenti attività di azioni predefinite: **[!UICONTROL Email]**, **[!UICONTROL Push]** e **[!UICONTROL SMS]**.

>[!NOTE]
>
>A questo scopo, devi configurare l’azione incorporata. Consulta [questa pagina](../action/working-with-adobe-campaign.md).

Per ciascuno di questi canali, seleziona una funzione di messaggistica transazionale di Adobe Campaign Standard **modello**. In effetti, [!DNL Journey Orchestration] non è una soluzione di invio di messaggi. Per i canali e-mail, SMS e push incorporati, ci affidiamo alla messaggistica transazionale per eseguire l’invio dei messaggi. Ciò significa che se desideri utilizzare un determinato modello di messaggio nei tuoi percorsi, devi pubblicarlo in Adobe Campaign Standard. Fai riferimento a [questa pagina](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=it) per scoprire come utilizzare questa funzione.

>[!NOTE]
>
>Per poter essere utilizzato nel Journey Orchestration, il messaggio transazionale Campaign Standard e il relativo evento associato devono essere pubblicati. Se l’evento viene pubblicato ma il messaggio non lo è, non sarà visibile nell’interfaccia di Journey Orchestration. Se il messaggio viene pubblicato ma il relativo evento associato non lo è, sarà visibile nell’interfaccia di Journey Orchestration ma non sarà utilizzabile.

![](../assets/journey59.png)

Puoi utilizzare un evento (noto anche come modello di messaggistica transazionale di profilo in tempo reale).

>[!NOTE]
>
>Quando inviamo messaggi transazionali in tempo reale (rtEvent) o quando inviamo messaggi con un sistema di terze parti grazie a un’azione personalizzata, è necessaria una configurazione specifica per la gestione dell’affaticamento, dell’elenco Bloccati o dell’annullamento dell’abbonamento. Ad esempio, se un attributo &quot;unsubscribe&quot; è memorizzato in Adobe Experience Platform o in un sistema di terze parti, sarà necessario aggiungere una condizione prima dell’invio del messaggio per verificare questa condizione.

Quando selezioni un modello, tutti i campi previsti nel payload del messaggio vengono visualizzati nel riquadro di configurazione dell’attività in **[!UICONTROL Address]** e **[!UICONTROL Personalization Data]**. Devi mappare ciascuno di questi campi con il campo che desideri utilizzare, dall’evento o dall’origine dati. È inoltre possibile utilizzare l’editor di espressioni avanzate per passare manualmente un valore, manipolare i dati sulle informazioni recuperate (ad esempio, convertire una stringa in maiuscolo) o utilizzare funzioni quali &quot;if, then, else&quot;. Consulta [questa pagina](../expression/expressionadvanced.md).

![](../assets/journey60.png)

## E-mail e SMS {#section_asc_51g_nhb}

Per **[!UICONTROL Email]** e **[!UICONTROL SMS]**, i parametri sono identici.

>[!NOTE]
>
>Per le e-mail, se utilizzi un modello transazionale di profili, il meccanismo di annullamento dell’abbonamento viene gestito da Campaign Standard in modo predefinito. È sufficiente aggiungere un’ **[!UICONTROL Unsubscription link]** blocco di contenuto nel modello ([ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=it)). Se utilizzi un modello basato su eventi (rtEvent), devi aggiungere nel messaggio un collegamento che trasmette l’e-mail della persona nel parametro URL e che punta a una pagina di destinazione per l’annullamento dell’abbonamento. Devi creare questa pagina di destinazione e assicurarti che la decisione della persona di annullare l’abbonamento sia trasmessa ad Adobe.

Innanzitutto, devi scegliere un modello di messaggistica transazionale. Consulta [questa pagina](../building-journeys/about-action-activities.md).

Sono disponibili due categorie: **[!UICONTROL Address]** e **[!UICONTROL Personalization Data]**.

È possibile definire facilmente dove recuperare **[!UICONTROL Address]** o **[!UICONTROL Personalization Data]** tramite l’interfaccia di. Puoi sfogliare gli eventi e i campi dell’origine dati disponibili. È inoltre possibile utilizzare l’editor di espressioni avanzate per casi di utilizzo più avanzati, ad esempio per utilizzare un’origine dati che richiede il passaggio di parametri o l’esecuzione di manipolazioni. Consulta [questa pagina](../expression/expressionadvanced.md).

**[!UICONTROL Address]**

>[!NOTE]
>
>Questa categoria è visibile solo se selezioni un messaggio transazionale &quot;evento&quot;. Per i messaggi di &quot;profilo&quot;, la **[!UICONTROL Address]** viene recuperato automaticamente da Adobe Campaign Standard.

Questi sono i campi necessari per sapere dove inviare il messaggio. Per un modello e-mail, si tratta dell’indirizzo e-mail. Per un SMS, è il numero del cellulare.

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Non è possibile trasmettere una raccolta nei dati di personalizzazione. Se l’e-mail o l’SMS transazionale prevede delle raccolte, non funzioneranno. Inoltre, i dati di personalizzazione hanno un formato previsto (ad esempio, stringa, decimale e così via). Devi fare attenzione a rispettare questi formati previsti.

Questi sono i campi previsti dal messaggio di Adobe Campaign Standard. Questi campi possono essere utilizzati per personalizzare il messaggio, applicare la formattazione condizionale o scegliere una variante di messaggio specifica.

![](../assets/journey62.png)

## Push {#section_im3_hvf_nhb}

Prima di utilizzare l’attività push, è necessario configurare l’app mobile e Campaign Standard per inviare le notifiche push. Usa questo [articolo](https://helpx.adobe.com/it/campaign/kb/integrate-mobile-sdk.html) per adottare le misure di implementazione necessarie per mobile.

Innanzitutto, devi scegliere un’app mobile dall’elenco a discesa e un messaggio transazionale. Consulta [questa pagina](../building-journeys/about-action-activities.md).

![](../assets/journey62bis.png)

Sono disponibili due categorie: **[!UICONTROL Target]** e **[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>Questa categoria è visibile solo se selezioni un messaggio evento. Per i messaggi di profilo, **[!UICONTROL Target]** I campi vengono recuperati automaticamente dal sistema utilizzando la riconciliazione eseguita da Adobe Campaign Standard.

In questa sezione devi definire **[!UICONTROL Push platform]**. L’elenco a discesa consente di selezionare **[!UICONTROL Apple Push Notification Server]** (iOS) oppure **[!UICONTROL Firebase Cloud Messaging]** (Android) In alternativa, puoi selezionare un campo specifico da un evento o da un’origine dati oppure definire un’espressione avanzata.

È inoltre necessario definire **[!UICONTROL Registration Token]**. L’espressione dipende da come viene definito il token nel payload dell’evento o in altri [!DNL Journey Orchestration] informazioni. Può essere un campo semplice o un’espressione più complessa, nel caso in cui il token sia definito in una raccolta, ad esempio:

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Non è possibile trasmettere una raccolta nei dati di personalizzazione. Se il push transazionale prevede delle raccolte, non funzionerà. Inoltre, i dati di personalizzazione hanno un formato previsto (ad esempio, stringa, decimale e così via). Devi fare attenzione a rispettare questi formati previsti.

Questi sono i campi previsti dal modello transazionale utilizzato nel messaggio di Adobe Campaign Standard. Questi campi possono essere utilizzati per personalizzare il messaggio, applicare la formattazione condizionale o scegliere una variante di messaggio specifica.
