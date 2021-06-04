---
product: adobe campaign
title: Utilizzo delle azioni di Adobe Campaign
description: Informazioni sulle azioni di Adobe Campaign
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: c49908d36ecbc68ae11b5621305f39dd59c67871
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 4%

---

# Utilizzo delle azioni di Adobe Campaign {#using_campaign_action}

## Utilizzo di Adobe Campaign Standard {#using_campaign_standard_action}

Se disponi di Adobe Campaign Standard, sono disponibili le seguenti attività di azione predefinite: **[!UICONTROL Email]**, **[!UICONTROL Push]** e **[!UICONTROL SMS]**.

>[!NOTE]
>
>A questo scopo, devi configurare l’azione incorporata. Consulta [questa pagina](../action/working-with-adobe-campaign.md).

Per ciascuno di questi canali, seleziona un modello di messaggistica transazionale Adobe Campaign Standard **template**. In effetti, [!DNL Journey Orchestration] non è una soluzione per l’invio di messaggi. Per i canali e-mail, SMS e push incorporati, ci affidiamo alla messaggistica transazionale per eseguire l’invio dei messaggi. Significa che se desideri utilizzare un determinato modello di messaggio nei tuoi percorsi, devi pubblicarlo in Adobe Campaign Standard. Per informazioni su come utilizzare questa funzione, consulta [questa pagina](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.translate.html) .

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

### E-mail e SMS {#section_asc_51g_nhb}

Per **[!UICONTROL Email]** e **[!UICONTROL SMS]**, i parametri sono identici.

>[!NOTE]
>
>Per l’e-mail, se utilizzi un modello transazionale di profili, il meccanismo di annullamento dell’abbonamento viene gestito come predefinito da Campaign Standard. È sufficiente aggiungere un blocco di contenuto **[!UICONTROL Unsubscription link]** nel modello ([ulteriori informazioni](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)). Se utilizzi un modello basato su eventi (rtEvent), devi aggiungere nel messaggio un collegamento che passa l’e-mail della persona nel parametro URL e punta a una pagina di destinazione per l’annullamento dell’abbonamento. Devi creare questa pagina di destinazione e accertarti che la decisione dell’utente di annullare l’iscrizione sia trasmessa all’Adobe.

Innanzitutto, devi scegliere un modello di messaggistica transazionale. Consulta [questa pagina](../building-journeys/about-action-activities.md).

Sono disponibili due categorie: **[!UICONTROL Address]** e **[!UICONTROL Personalization Data]**.

Puoi definire facilmente dove recuperare il **[!UICONTROL Address]** o il **[!UICONTROL Personalization Data]** utilizzando l&#39;interfaccia . È possibile sfogliare gli eventi e i campi dell’origine dati disponibili. Puoi inoltre utilizzare l’editor di espressioni avanzate per casi d’uso più avanzati, ad esempio per utilizzare un’origine dati che richiede il passaggio di parametri o l’esecuzione di manipolazioni. Consulta [questa pagina](../expression/expressionadvanced.md).

**[!UICONTROL Address]**

>[!NOTE]
>
>Questa categoria è visibile solo se selezioni un messaggio transazionale &quot;evento&quot;. Per i messaggi &quot;profile&quot;, il campo **[!UICONTROL Address]** viene recuperato automaticamente da Adobe Campaign Standard dal sistema.

Questi sono i campi necessari al sistema per sapere dove inviare il messaggio. Per un modello e-mail, si tratta dell’indirizzo e-mail. Per un SMS, è il numero di telefono cellulare.

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Non puoi passare una raccolta nei dati di personalizzazione. Se l’e-mail o l’SMS sulle transazioni prevede delle raccolte, non funzionerà. Tieni presente anche che i dati di personalizzazione hanno un formato previsto (ad esempio: (stringa, decimale, ecc.). Devi fare attenzione a rispettare questi formati previsti.

Questi sono i campi previsti dal messaggio Adobe Campaign Standard. Questi campi possono essere utilizzati per personalizzare il messaggio, applicare la formattazione condizionale o scegliere una specifica variante del messaggio.

![](../assets/journey62.png)

### Push {#section_im3_hvf_nhb}

Prima di utilizzare l’attività push, è necessario configurare la tua app mobile insieme a Campaign Standard per l’invio di notifiche push. Utilizza questo [articolo](https://helpx.adobe.com/it/campaign/kb/integrate-mobile-sdk.html) per intraprendere i passaggi di implementazione necessari per mobile.

Innanzitutto, devi scegliere un’app mobile dall’elenco a discesa e un messaggio transazionale. Consulta [questa pagina](../building-journeys/about-action-activities.md).

![](../assets/journey62bis.png)

Sono disponibili due categorie: **[!UICONTROL Target]** e **[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>Questa categoria è visibile solo se selezioni un messaggio evento. Per i messaggi di profilo, i campi **[!UICONTROL Target]** vengono recuperati automaticamente dal sistema utilizzando la riconciliazione eseguita da Adobe Campaign Standard.

In questa sezione, devi definire il valore **[!UICONTROL Push platform]**. L’elenco a discesa consente di selezionare **[!UICONTROL Apple Push Notification Server]** (iOS) o **[!UICONTROL Firebase Cloud Messaging]** (Android). In alternativa, puoi selezionare un campo specifico da un evento o un’origine dati oppure definire un’espressione avanzata.

È inoltre necessario definire il parametro **[!UICONTROL Registration Token]**. L’espressione dipende dalla modalità di definizione del token nel payload dell’evento o in altre informazioni [!DNL Journey Orchestration] . Può essere un campo semplice o un’espressione più complessa nel caso in cui il token sia definito in una raccolta, ad esempio:

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>Non puoi passare una raccolta nei dati di personalizzazione. Se il push transazionale prevede raccolte, non funzionerà. Tieni presente anche che i dati di personalizzazione hanno un formato previsto (ad esempio: (stringa, decimale, ecc.). Devi fare attenzione a rispettare questi formati previsti.

Questi sono i campi previsti dal modello transazionale utilizzato nel messaggio Adobe Campaign Standard. Questi campi possono essere utilizzati per personalizzare il messaggio, applicare la formattazione condizionale o scegliere una specifica variante del messaggio.

## Utilizzo di Adobe Campaign v7/v8 {#using_campaign_v7_v8_action}

Questa integrazione è disponibile per Adobe Campaign Classic v7 a partire dalla versione 21.1 e Adobe Campaign v8. Ti consentirà di inviare e-mail, notifiche push e SMS utilizzando le funzionalità di messaggistica transazionale di Adobe Campaign.

La connessione tra le istanze del Journey Orchestration e di Campaign viene impostata per Adobe al momento del provisioning. Adobe di contatto.

Affinché questo funzioni, devi configurare un’azione dedicata. Fare riferimento a questa sezione [sezione](../action/working-with-adobe-campaign.md#using_adobe_campaign_v7_v8).

In questa [sezione](../usecase/campaign-v7-v8-use-case.md) viene presentato un caso d’uso end-to-end.

1. Progetta il tuo percorso, a partire da un evento. Vedere questa sezione [](../building-journeys/journey.md).
1. Nella sezione **Azione** della palette, seleziona un’azione Campaign e aggiungilo al percorso.
1. Nei **Parametri azione** vengono visualizzati tutti i campi previsti nel payload del messaggio. Devi mappare ciascuno di questi campi con il campo che desideri utilizzare, dall’evento o dall’origine dati. È simile alle azioni personalizzate. Fare riferimento a questa sezione [sezione](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)

