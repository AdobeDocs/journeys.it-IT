---
product: adobe campaign
title: Funzioni di gestione delle raccolte
description: Informazioni sui tipi di dati nelle funzioni di gestione delle raccolte
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 2%

---

# Funzioni di gestione delle raccolte {#collection-management-functions}

Il linguaggio delle espressioni introduce anche un set di funzioni per le raccolte di query.

Queste funzioni sono descritte di seguito. Negli esempi seguenti, utilizziamo il payload dell’evento contenente una raccolta:

```json
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

Il **[!UICONTROL all]** funzione consente di definire un filtro per una determinata raccolta utilizzando un&#39;espressione booleana.

```json
<listExpression>.all(<condition>)
```

Ad esempio, tra tutti gli utenti dell’app, puoi ottenere quelli che utilizzano IOS 13 (espressione booleana &quot;app utilizzata == IOS 13&quot;). Il risultato di questa funzione è l’elenco filtrato contenente gli elementi che corrispondono all’espressione booleana (ad esempio: utente app 1, utente app 34, utente app 432).

In un’attività Data Source Condition puoi verificare se il risultato della **[!UICONTROL all]** la funzione è null o no. Puoi anche combinare questo **[!UICONTROL all]** con altre funzioni quali **[!UICONTROL count]**. Per ulteriori informazioni, consulta [Attività condizione origine dati](../building-journeys/condition-activity.md#data_source_condition).

**Esempio 1:**

Vogliamo verificare se un utente ha installato una versione specifica di un’applicazione. Per questo otteniamo tutti i token di notifica push associati alle applicazioni mobili per le quali la versione è 1.0. Quindi, viene eseguita una condizione con **[!UICONTROL count]** per verificare che l’elenco di token restituito contenga almeno un elemento.

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

Il risultato è vero.

**Esempio 2:**

In questo caso utilizziamo **[!UICONTROL count]** per verificare se la raccolta contiene token di notifica push.

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

Il risultato sarà vero.

<!--Alternatively, you can check if there is no token in the collection:

   ```json
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
>Quando la condizione di filtro in **all()** è vuoto, il filtro restituirà tutti gli elementi nell’elenco. **Tuttavia, per contare il numero di elementi di una raccolta, non è necessaria la funzione all.**


```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

Il risultato dell’espressione è **3**.

**Esempio 3:**

Qui controlliamo se un individuo non ha ricevuto alcuna comunicazione nelle ultime 24 ore. La raccolta di eventi di esperienza recuperata dall’origine dati di Experience Platform viene filtrata utilizzando due espressioni basate su due elementi della raccolta. In particolare, la marca temporale dell’evento viene confrontata con la data/ora restituita dal **[!UICONTROL nowWithDelta]** funzione.

```json
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

Il risultato sarà vero se non c’è un evento esperienza che corrisponde alle due condizioni.

**Esempio 4:**

Qui vogliamo verificare se un singolo utente ha avviato un’applicazione almeno una volta negli ultimi 7 giorni, ad esempio per attivare una notifica push che invita l’utente ad avviare un’esercitazione.

```json
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
>**[!UICONTROL currentEventField]** è disponibile solo quando si manipolano le raccolte di eventi e **currentDataPackField**
>durante la manipolazione delle raccolte di origini dati. Durante l’elaborazione delle raccolte con **[!UICONTROL all]**, **[!UICONTROL first]** e **[!UICONTROL last]**, noi
>ciclo su ogni elemento della raccolta uno alla volta. **[!UICONTROL currentEventField]** e **currentDataPackField**
>corrisponde all&#39;elemento di cui viene eseguito il ciclo.

**Le funzioni &quot;first(`<condition>`)&quot; e &quot;last(`<condition>`)&quot;**

Il **[!UICONTROL first]** e **[!UICONTROL last]** Le funzioni consentono inoltre di definire un filtro per la raccolta restituendo il primo/ultimo elemento dell&#39;elenco che soddisfa il filtro.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Esempio 1:**

Questa espressione restituisce il primo token di notifica push associato alle applicazioni mobili la cui versione è 1.0.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

Il risultato è &quot;token_1&quot;.

**Esempio 2:**

Questa espressione restituisce l’ultimo token di notifica push associato alle applicazioni mobili la cui versione è 1.0.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

Il risultato è &quot;token_2&quot;.

>[!NOTE]
>
>Gli eventi esperienza vengono recuperati da Adobe Experience Platform come una raccolta in ordine cronologico inverso, quindi:
>
>* **[!UICONTROL first]** restituirà l’evento più recente
>* **[!UICONTROL last]** restituirà quella più vecchia.


**Esempio 3:**

Verifichiamo se il primo evento Adobe Analytics (più recente) con un valore diverso da zero per l’ID DMA ha un valore uguale a 602.

```json
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**La funzione &quot;at(`<index>`)&quot;**

Il **[!UICONTROL at]** funzione consente di fare riferimento a un elemento specifico di una raccolta in base a un indice.
L&#39;indice 0 è il primo indice della raccolta.

_`<listExpression>`.at(`<index>`)_

**Esempio:**

Questa espressione restituisce il secondo token di notifica push dell’elenco.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

Il risultato è &quot;token_2&quot;.

**Altri esempi**

```json
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```json
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
