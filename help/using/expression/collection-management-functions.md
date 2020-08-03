---
title: Funzioni di gestione delle raccolte
description: Informazioni sui tipi di dati nelle funzioni di gestione della raccolta
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---


# Funzioni di gestione delle raccolte {#collection-management-functions}

Il linguaggio di espressione introduce anche un set di funzioni per eseguire query sulle raccolte.

Queste funzioni sono spiegate di seguito. Negli esempi seguenti, utilizziamo il payload dell&#39;evento contenente una raccolta:

```
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**La funzione &quot;all(`<condition>`)&quot;**

La **[!UICONTROL all]** funzione abilita la definizione di un filtro su una determinata raccolta utilizzando un&#39;espressione booleana.

```
<listExpression>.all(<condition>)
```

Ad esempio, tra tutti gli utenti dell&#39;app, potete ottenere quelli che utilizzano IOS 13 (espressione booleana &quot;app utilizzata == IOS 13&quot;). Il risultato di questa funzione è l&#39;elenco filtrato contenente elementi corrispondenti all&#39;espressione booleana (esempio: app user 1, app user 34, app user 432).

In un&#39;attività Condizione origine dati è possibile verificare se il risultato della **[!UICONTROL all]** funzione è nullo o meno. È inoltre possibile combinare questa **[!UICONTROL all]** funzione con altre funzioni, ad esempio **[!UICONTROL count]**. Per ulteriori informazioni, consulta Attività [Condizione origine](../building-journeys/condition-activity.md#data_source_condition)dati.

**Esempio 1:**

Vogliamo verificare se un utente ha installato una versione specifica di un&#39;applicazione. A questo scopo, tutti i token di notifica push vengono associati alle applicazioni mobili la cui versione è 1.0. Quindi, viene eseguita una condizione con la **[!UICONTROL count]** funzione per verificare che l&#39;elenco restituito di token contenga almeno un elemento.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

Il risultato è vero.

**Esempio 2:**

In questa sezione utilizziamo la **[!UICONTROL count]** funzione per verificare se nella raccolta sono presenti token di notifica push.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

Il risultato sarà vero.

<!--Alternatively, you can check if there is no token in the collection:

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the Adobe Experience Platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the Adobe Experience Platform. For example, when using the .all() syntax to query experience events from the Adobe Experience Platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>Quando la condizione di filtro nella funzione **all()** è vuota, il filtro restituirà tutti gli elementi nell&#39;elenco. **Tuttavia, per conteggiare il numero di elementi di una raccolta, la funzione all non è obbligatoria.**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

Il risultato dell&#39;espressione è **3**.

**Esempio 3:**

Qui verifichiamo se un individuo non ha ricevuto alcuna comunicazione entro le ultime 24 ore. Filtriamo la raccolta di eventi esperienza recuperati dall&#39;origine dati ExperiencePlatform utilizzando due espressioni basate su due elementi della raccolta. In particolare, la marca temporale dell&#39;evento viene confrontata con la dataTime restituita dalla **[!UICONTROL nowWithDelta]** funzione.

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

Il risultato sarà vero se non esiste un evento esperienza che corrisponda alle due condizioni.

**Esempio 4:**

Qui si desidera verificare se un individuo ha avviato almeno una volta un&#39;applicazione negli ultimi 7 giorni, ad esempio per attivare una notifica push invitandolo ad avviare un&#39;esercitazione.

```
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```

<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]** è disponibile solo quando si modificano le raccolte di eventi e **currentDataPackField**
>durante la manipolazione delle raccolte di origini dati. Durante l&#39;elaborazione delle raccolte con **[!UICONTROL all]**, **[!UICONTROL first]** e **[!UICONTROL last]**
>su ciascun elemento della raccolta, uno per uno. **[!UICONTROL currentEventField]** e **currentDataPackField**
>corrisponde all’elemento a cui viene ripetuto il ciclo.

**Le funzioni &quot;first(`<condition>`)&quot; e &quot;last(`<condition>`)&quot;**

Le funzioni **[!UICONTROL first]** e **[!UICONTROL last]** consentono inoltre la definizione di un filtro nella raccolta restituendo il primo o l&#39;ultimo elemento dell&#39;elenco che soddisfa il filtro.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Esempio 1:**

Questa espressione restituisce il primo token di notifica push associato alle applicazioni mobili la cui versione è 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

Il risultato è &quot;token_1&quot;.

**Esempio 2:**

Questa espressione restituisce l&#39;ultimo token di notifica push associato alle applicazioni mobili la cui versione è 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

Il risultato è &quot;token_2&quot;.

>[!NOTE]
>
>Gli eventi esperienza vengono recuperati dal Adobe Experience Platform  come raccolta in ordine cronologico inverso, di conseguenza:
>* **[!UICONTROL first]** restituirà l&#39;evento più recente
>* **[!UICONTROL last]** restituirà la funzione meno recente.


**Esempio 3:**

Verifichiamo che il primo (più recente) evento  Adobe Analytics con un valore diverso da zero per l&#39;ID DMA abbia un valore pari a 602.

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**La funzione &quot;at(`<index>`)&quot;**

La **[!UICONTROL at]** funzione consente di fare riferimento a un elemento specifico in una raccolta in base a un indice.
L&#39;indice 0 è il primo indice della raccolta.

_`<listExpression>`.at(`<index>`)_

**Esempio:**

Questa espressione restituisce il secondo token di notifica push dell&#39;elenco.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

Il risultato è &quot;token_2&quot;.