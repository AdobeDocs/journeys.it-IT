---
product: adobe campaign
solution: Journey Orchestration
title: Riferimenti campo
description: Informazioni sui riferimenti di campo nelle espressioni avanzate
translation-type: tm+mt
source-git-commit: e2f7c39e61118c42272f730cf5f688ee34d6a9c2
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 3%

---



# Riferimenti campo {#concept_fkj_ll5_dgb}

Un riferimento a un campo può essere allegato a un evento o a un gruppo di campi. L’unica informazione significativa è il nome del campo e il relativo percorso.

Se si utilizzano caratteri speciali in un campo, è necessario utilizzare virgolette doppie o virgolette semplici. Di seguito sono riportati i casi in cui sono necessarie delle virgolette:

* il campo inizia con caratteri numerici
* il campo inizia con il carattere &quot;-&quot;
* il campo contiene elementi diversi da: _a_-_z_, _A_-_Z_, _0_-___9, _, -_

Ad esempio, se il campo è di _3 ore_: _#{OpenWeather.WeatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

Nell&#39;espressione, ai campi dell&#39;evento viene fatto riferimento con &quot;@&quot; e ai campi dell&#39;origine dati viene fatto riferimento con &quot;#&quot;.

Un colore della sintassi viene utilizzato per distinguere visivamente i campi evento (verde) dai gruppi di campi (blu).

**Valori predefiniti per i riferimenti di campo**

Un valore predefinito può essere associato a un nome di campo. La sintassi è la seguente:

```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>Il tipo di campo e il valore predefinito devono essere identici. Ad esempio, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} non sarà valido perché il valore predefinito è un numero intero, mentre il valore previsto dovrebbe essere una stringa.

Esempi:

```
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

**Riferimento di un campo all&#39;interno delle raccolte**

Agli elementi definiti all&#39;interno delle raccolte viene fatto riferimento utilizzando le funzioni specifiche all, first e last. Per ulteriori informazioni, consulta [questa pagina](../expression/collection-management-functions.md).

Esempio :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Riferimento a un campo definito in una mappa**

Per recuperare un elemento in una mappa, utilizziamo la funzione di immissione con una data chiave. Ad esempio, viene utilizzato quando si definisce la chiave di un evento, in base allo spazio dei nomi selezionato. Vedere Selezione dello spazio dei nomi. Per ulteriori informazioni, consultate [questa pagina](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

In questa espressione, è disponibile la voce per la chiave ‘Email’ del campo ‘IdentityMap’ di un evento. La voce &quot;E-mail&quot; è una raccolta, dalla quale prendiamo l&#39;&quot;id&quot; nel primo elemento utilizzando &quot;first()&quot;. Per ulteriori informazioni, consultate [questa pagina](../expression/collection-management-functions.md).

**Valori di parametro di un&#39;origine dati (valori dinamici dell&#39;origine dati)**

Se si seleziona un campo da un&#39;origine dati esterna che richiede la chiamata di un parametro, viene visualizzata una nuova scheda a destra che consente di specificare questo parametro. Consulta [questa pagina](../expression/expressionadvanced.md).

For more complex use cases, if you want to include the parameters of the data source in the main expression, you can define their values using the keyword _params_. Un parametro può essere una qualsiasi espressione valida anche da un&#39;altra origine dati che include anche un altro parametro.

>[!NOTE]
>
>Quando definite i valori dei parametri nell&#39;espressione, la scheda a destra scompare.

Utilizzate la sintassi seguente:

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: nome esatto del primo parametro dall&#39;origine dati.
* **`<params-1-value>`**: il valore del primo parametro. Può essere una qualsiasi espressione valida.

Esempio:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
