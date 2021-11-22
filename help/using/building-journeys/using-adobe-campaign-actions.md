---
product: adobe campaign
title: Utilizzo delle azioni di Adobe Campaign
description: Informazioni sulle azioni di Adobe Campaign
feature: Journeys
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 5%

---

# Utilizzo di Adobe Campaign Standard {#using_campaign_action}

Se disponi di Adobe Campaign Standard, sono disponibili le seguenti attività di azione predefinite: **[!UICONTROL Email]**, **[!UICONTROL Push]** e **[!UICONTROL SMS]**.

>[!NOTE]
>
>A questo scopo, devi configurare l’azione incorporata. Consulta [questa pagina](../action/working-with-adobe-campaign.md).

Per ciascuno di questi canali, seleziona una messaggistica transazionale Adobe Campaign Standard **template**. Infatti, [!DNL Journey Orchestration] non è una soluzione per l’invio di messaggi. Per i canali e-mail, SMS e push incorporati, ci affidiamo alla messaggistica transazionale per eseguire l’invio dei messaggi. Significa che se desideri utilizzare un determinato modello di messaggio nei tuoi percorsi, devi pubblicarlo in Adobe Campaign Standard. Fai riferimento a [questa pagina](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=it) per scoprire come utilizzare questa funzione.

>[!NOTE]
>
>Per poter essere utilizzato nel Journey Orchestration, il messaggio transazionale di Campaign Standard e il relativo evento associato devono essere pubblicati. Se l’evento è pubblicato ma il messaggio non lo è, non sarà visibile nell’interfaccia di Journey Orchestration. Se il messaggio viene pubblicato ma l’evento associato non lo è, sarà visibile nell’interfaccia di Journey Orchestration ma non sarà utilizzabile.

![](../assets/journey59.png)

Puoi utilizzare un evento (noto anche come in tempo reale) o un modello di messaggistica transazionale di profilo.

>[!NOTE]
>
>Quando inviamo messaggi transazionali in tempo reale (rtEvent) o quando inviamo messaggi con un sistema di terze parti tramite un’azione personalizzata, è necessaria una configurazione specifica per la gestione dell’affaticamento, dell’elenco Bloccati o dell’annullamento dell’abbonamento. Ad esempio, se un attributo &quot;Annulla sottoscrizione&quot; è memorizzato in Adobe Experience Platform o in un sistema di terze parti, prima che il messaggio di invio verifichi questa condizione sarà necessario aggiungere una condizione.

Quando selezioni un modello, tutti i campi previsti nel payload del messaggio vengono visualizzati nel riquadro di configurazione dell’attività in **[!UICONTROL Address]** e **[!UICONTROL Personalization Data]**. Devi mappare ciascuno di questi campi con il campo che desideri utilizzare, dall’evento o dall’origine dati. È inoltre possibile utilizzare l’editor di espressioni avanzate per passare manualmente un valore, eseguire la manipolazione dei dati sulle informazioni recuperate (ad esempio convertire una stringa in maiuscolo) o utilizzare funzioni come &quot;if, then, else&quot;. Consulta [questa pagina](../expression/expressionadvanced.md).

![](../assets/journey60.png)

## E-mail e SMS {#section_asc_51g_nhb}

Per **[!UICONTROL Email]** e **[!UICONTROL SMS]**, i parametri sono identici.

>[!NOTE]
>
>Per l’e-mail, se utilizzi un modello transazionale di profili, il meccanismo di annullamento dell’abbonamento viene gestito come predefinito da Campaign Standard. Aggiungi semplicemente un **[!UICONTROL Unsubscription link]** blocco di contenuto nel modello ([ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html)). Se utilizzi un modello basato su eventi (rtEvent), devi aggiungere nel messaggio un collegamento che passa l’e-mail della persona nel parametro URL e punta a una pagina di destinazione per l’annullamento dell’abbonamento. Devi creare questa pagina di destinazione e accertarti che la decisione dell’utente di annullare l’iscrizione sia trasmessa all’Adobe.

Innanzitutto, devi scegliere un modello di messaggistica transazionale. Consulta [questa pagina](../building-journeys/about-action-activities.md).

Sono disponibili due categorie: **[!UICONTROL Address]** e **[!UICONTROL Personalization Data]**.

Puoi definire facilmente dove recuperare il **[!UICONTROL Address]** o **[!UICONTROL Personalization Data]** utilizzando l’interfaccia . È possibile sfogliare gli eventi e i campi dell’origine dati disponibili. Puoi inoltre utilizzare l’editor di espressioni avanzate per casi d’uso più avanzati, ad esempio per utilizzare un’origine dati che richiede il passaggio di parametri o l’esecuzione di manipolazioni. Consulta [questa pagina](../expression/expressionadvanced.md).

**[!UICONTROL Address]**

>[!NOTE]
>
>Questa categoria è visibile solo se selezioni un messaggio transazionale &quot;evento&quot;. Per i messaggi &quot;profile&quot;, la **[!UICONTROL Address]** Il campo viene recuperato automaticamente da Adobe Campaign Standard dal sistema.

Questi sono i campi necessari al sistema per sapere dove inviare il messaggio. Per un modello e-mail, si tratta dell’indirizzo e-mail. Per un SMS, è il numero di telefono cellulare.

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Non puoi passare una raccolta nei dati di personalizzazione. Se l’e-mail o l’SMS sulle transazioni prevede delle raccolte, non funzionerà. Tieni presente anche che i dati di personalizzazione hanno un formato previsto (ad esempio: (stringa, decimale, ecc.). Devi fare attenzione a rispettare questi formati previsti.

Questi sono i campi previsti dal messaggio Adobe Campaign Standard. Questi campi possono essere utilizzati per personalizzare il messaggio, applicare la formattazione condizionale o scegliere una specifica variante del messaggio.

![](../assets/journey62.png)

## Push {#section_im3_hvf_nhb}

Prima di utilizzare l’attività push, è necessario configurare la tua app mobile insieme a Campaign Standard per l’invio di notifiche push. Utilizza questo [articolo](https://helpx.adobe.com/it/campaign/kb/integrate-mobile-sdk.html) adottare le misure di implementazione necessarie per mobile.

Innanzitutto, devi scegliere un’app mobile dall’elenco a discesa e un messaggio transazionale. Consulta [questa pagina](../building-journeys/about-action-activities.md).

![](../assets/journey62bis.png)

Sono disponibili due categorie: **[!UICONTROL Target]** e **[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>Questa categoria è visibile solo se selezioni un messaggio evento. Per i messaggi di profilo, la **[!UICONTROL Target]** i campi vengono recuperati automaticamente dal sistema utilizzando la riconciliazione eseguita da Adobe Campaign Standard.

In questa sezione, devi definire le **[!UICONTROL Push platform]**. L’elenco a discesa ti consente di selezionare **[!UICONTROL Apple Push Notification Server]** (iOS) o **[!UICONTROL Firebase Cloud Messaging]** (Android). In alternativa, puoi selezionare un campo specifico da un evento o un’origine dati oppure definire un’espressione avanzata.

È inoltre necessario definire le **[!UICONTROL Registration Token]**. L’espressione dipende dalla modalità di definizione del token nel payload dell’evento o in un altro [!DNL Journey Orchestration] informazioni. Può essere un campo semplice o un’espressione più complessa nel caso in cui il token sia definito in una raccolta, ad esempio:

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Non puoi passare una raccolta nei dati di personalizzazione. Se il push transazionale prevede raccolte, non funzionerà. Tieni presente anche che i dati di personalizzazione hanno un formato previsto (ad esempio: (stringa, decimale, ecc.). Devi fare attenzione a rispettare questi formati previsti.

Questi sono i campi previsti dal modello transazionale utilizzato nel messaggio Adobe Campaign Standard. Questi campi possono essere utilizzati per personalizzare il messaggio, applicare la formattazione condizionale o scegliere una specifica variante del messaggio.
