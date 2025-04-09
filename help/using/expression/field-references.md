---
product: adobe campaign
title: Riferimenti campo
description: Scopri i riferimenti ai campi nelle espressioni avanzate
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 2%

---

# Riferimenti campo {#concept_fkj_ll5_dgb}


>[!CAUTION]
>
>**Cerchi Adobe Systems Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy che sono stati sostituiti da Journey Optimizer. Contatta il team del tuo account in caso di domande sull&#39;accesso a Journey Orchestration o Journey Optimizer._


Un riferimento di campo può essere allegato a un evento o a un gruppo di campi. L’unica informazione significativa è il nome del campo e il relativo percorso.

Se in un campo si utilizzano caratteri speciali, è necessario utilizzare virgolette doppie o semplici. Di seguito sono riportati i casi in cui sono necessarie virgolette:

* Il campo inizia con caratteri numerici
* Il campo inizia con il carattere &quot;-&quot;
* il campo contiene elementi diversi da: _a-z___, _A-Z___, _0-9___, _ , - __

Ad esempio, se il campo è _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

Nell’espressione, ai campi evento viene fatto riferimento con &quot;@&quot; e ai campi dell’origine dati viene fatto riferimento con &quot;#&quot;.

Un colore di sintassi viene utilizzato per distinguere visivamente i campi degli eventi (verde) dai gruppi di campi (blu).

## Valori predefiniti per i riferimenti ai campi {#default-value}

Un valore predefinito può essere associato a un nome di campo. La sintassi è la seguente:

```json
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>Il tipo del campo e il valore predefinito devono essere uguali. Ad esempio, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} verrà non valido perché il valore predefinito è un numero intero mentre il valore previsto deve essere una stringa.

Esempi:

```json
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

È possibile aggiungere qualsiasi tipo di espressione come valore predefinito. L’unico vincolo è che l’espressione deve restituire il tipo di dati previsto. Quando si utilizza una funzione, è necessario incapsularla con ().

```
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.any.time, defaultValue : (now())} 
== date("2022-02-10T00:00:00Z")
```

## Riferimento a un campo all’interno di raccolte

Si fa riferimento agli elementi definiti nelle raccolte utilizzando le funzioni specifiche `all`, `first` e `last`. Per ulteriori informazioni, consulta [questa pagina](../expression/collection-management-functions.md).

Esempio:

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## Riferimento a un campo definito in una mappa

### Funzione `entry`

Per recuperare un elemento in una mappa, utilizziamo la funzione di immissione con una determinata chiave. Ad esempio, viene utilizzato quando si definisce la chiave di un evento, in base allo spazio dei nomi selezionato. Consulta Selezione dello spazio dei nomi. Per ulteriori informazioni, vedere [questa pagina](../event/selecting-the-namespace.md).

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

In questa espressione, stiamo ottenendo la voce per la chiave &#39;Email&#39; del campo &#39;IdentityMap&#39; di un evento. La voce &#39;Email&#39; è un raccolta, da cui prendiamo l&#39;id&#39; nel primo elemento usando &#39;first()&#39;. Per maggiori informazioni, consulta [questa pagina](../expression/collection-management-functions.md).

### `firstEntryKey` funzione

Per recuperare la prima chiave di ingresso di una mappa, utilizzare la funzione `firstEntryKey`.

Questo esempio mostra come recuperare il primo indirizzo e-mail degli abbonati di un elenco specifico:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

In questo esempio, l&#39;elenco iscrizioni è denominato `daily-email`. Gli indirizzi e-mail sono definiti come chiavi nella `subscribers` mappa, che è collegata alla mappa dell&#39;elenco delle sottoscrizioni.

### `keys` funzione

Per recuperare tutti i tasti di una mappa, utilizzare la `keys` funzione.

Questo esempio mostra come recuperare, per un profilo specifico, tutti gli indirizzi e-mail associati ai sottoscrittori di un elenco specifico:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## Valori dei parametri di un&#39;origine dati (valori dinamici dell&#39;origine dati)

Se si seleziona un campo da un&#39;origine dati esterna che richiede la chiamata di un parametro, viene visualizzato un nuovo scheda a destra che consente di specificare tale parametro. Consulta [questa pagina](../expression/expressionadvanced.md).

Per casi d&#39;uso più complessi, se desideri includere i parametri dell&#39;origine dati nell&#39;espressione principale, puoi definirne i valori utilizzando la parola chiave _params_. Un parametro può essere qualsiasi espressione valida anche da un&#39;altra origine dati che include anche un altro parametro.

>[!NOTE]
>
>Quando definite i valori dei parametri nell&#39;espressione, la linguetta a destra scompare.

Utilizza la seguente sintassi:

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: nome esatto del primo parametro dall&#39;origine dati.
* **`<params-1-value>`**: valore del primo parametro. Può essere qualsiasi espressione valida.

Esempio:

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
