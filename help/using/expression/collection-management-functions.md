---
product: adobe campaign
title: Funzioni di gestione delle raccolte
description: Informazioni sui tipi di dati nelle funzioni di gestione della raccolta
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 1%

---

# Funzioni di gestione delle raccolte {#collection-management-functions}

Il linguaggio di espressione introduce anche un set di funzioni per eseguire query sulle raccolte.

Queste funzioni sono spiegate di seguito. Negli esempi seguenti, utilizziamo il payload dell’evento contenente una raccolta:

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

La funzione **[!UICONTROL all]** abilita la definizione di un filtro su una determinata raccolta utilizzando un&#39;espressione booleana.

```
<listExpression>.all(<condition>)
```

Ad esempio, tra tutti gli utenti dell’app, puoi ottenere quelli che utilizzano IOS 13 (espressione booleana &quot;app used == IOS 13&quot;). Il risultato di questa funzione è l’elenco filtrato contenente elementi che corrispondono all’espressione booleana (esempio: utente app 1, utente app 34, utente app 432).

In un’attività Condizione origine dati puoi verificare se il risultato della funzione **[!UICONTROL all]** è nullo o meno. È inoltre possibile combinare questa funzione **[!UICONTROL all]** con altre funzioni come **[!UICONTROL count]**. Per ulteriori informazioni, consulta [Attività condizione origine dati](../building-journeys/condition-activity.md#data_source_condition).

**Esempio 1:**

Vogliamo verificare se un utente ha installato una versione specifica di un&#39;applicazione. A questo scopo, otteniamo tutti i token di notifica push associati alle applicazioni mobili per le quali la versione è 1.0. Quindi, eseguiamo una condizione con la funzione **[!UICONTROL count]** per verificare che l’elenco restituito di token contenga almeno un elemento.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

Il risultato è vero.

**Esempio 2:**

Qui usiamo la funzione **[!UICONTROL count]** per verificare se nella raccolta sono presenti token di notifica push.

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
>Quando la condizione di filtro nella funzione **all()** è vuota, il filtro restituirà tutti gli elementi dell&#39;elenco. **Tuttavia, per contare il numero di elementi di una raccolta, la funzione all non è necessaria.**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

Il risultato dell&#39;espressione è **3**.

**Esempio 3:**

Qui verifichiamo se un individuo non ha ricevuto alcuna comunicazione entro le ultime 24 ore. Filtriamo la raccolta di eventi di esperienza recuperati dall’origine dati Experience Platform, utilizzando due espressioni basate su due elementi della raccolta. In particolare, la marca temporale dell&#39;evento viene confrontata con la dataTime restituita dalla funzione **[!UICONTROL nowWithDelta]** .

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

Il risultato sarà vero se non esiste un evento di esperienza che corrisponda alle due condizioni.

**Esempio 4:**

Qui vogliamo verificare se una persona ha avviato almeno una volta un’applicazione negli ultimi 7 giorni, per esempio per attivare una notifica push invitandola ad avviare un’esercitazione.

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
>**[!UICONTROL currentEventField]** è disponibile solo durante la manipolazione delle raccolte di eventi e  **currentDataPackField**
>durante la manipolazione delle raccolte di origini dati. Quando elaboriamo le raccolte con **[!UICONTROL all]**, **[!UICONTROL first]** e **[!UICONTROL last]**,
>su ogni elemento della raccolta, uno per uno. **[!UICONTROL currentEventField]** e  **currentDataPackField**
>corrispondono all’elemento a cui si sta ripetendo il ciclo.

**Le funzioni &quot;first(`<condition>`)&quot; e &quot;last(`<condition>`)&quot;**

Le funzioni **[!UICONTROL first]** e **[!UICONTROL last]** consentono inoltre di definire un filtro per la raccolta restituendo al contempo il primo/ultimo elemento dell’elenco che soddisfa il filtro.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Esempio 1:**

Questa espressione restituisce il primo token di notifica push associato alle applicazioni mobili la cui versione è 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

Il risultato è &quot;token_1&quot;.

**Esempio 2:**

Questa espressione restituisce l’ultimo token di notifica push associato alle applicazioni mobili la cui versione è 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

Il risultato è &quot;token_2&quot;.

>[!NOTE]
>
>Gli eventi di esperienza vengono recuperati da Adobe Experience Platform come raccolta in ordine cronologico inverso, quindi :
>* **[!UICONTROL first]** restituirà l’evento più recente
>* **[!UICONTROL last]** restituirà quello più vecchio.


**Esempio 3:**

Controlliamo se il primo evento Adobe Analytics (più recente) con un valore diverso da zero per DMA ID ha un valore pari a 602.

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**La funzione &quot;at(`<index>`)&quot;**

La funzione **[!UICONTROL at]** ti consente di fare riferimento a un elemento specifico in una raccolta in base a un indice.
L&#39;indice 0 è il primo indice della raccolta.

_`<listExpression>`.at(`<index>`)_

**Esempio:**

Questa espressione restituisce il secondo token di notifica push dell’elenco.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

Il risultato è &quot;token_2&quot;.
