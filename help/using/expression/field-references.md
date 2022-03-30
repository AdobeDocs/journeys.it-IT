---
product: adobe campaign
title: Riferimenti campo
description: Informazioni sui riferimenti di campo nelle espressioni avanzate
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: bb07c0edaae469962ee3bf678664b4a0a83572fe
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 3%

---

# Riferimenti campo {#concept_fkj_ll5_dgb}

Un riferimento di campo può essere associato a un evento o a un gruppo di campi. L’unica informazione significativa è il nome del campo e il relativo percorso.

Se utilizzi caratteri speciali in un campo, devi utilizzare virgolette doppie o virgolette semplici. Di seguito sono riportati i casi in cui le virgolette sono necessarie:

* il campo inizia con caratteri numerici
* il campo inizia con il carattere &quot;-&quot;
* il campo contiene elementi diversi da: _a_-_z_, _A_-_Z_, _0_-_9_, _ , _-_

Ad esempio se il campo è _3 h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

Nell&#39;espressione, ai campi evento viene fatto riferimento con &quot;@&quot; e ai campi dell&#39;origine dati viene fatto riferimento con &quot;#&quot;.

Il colore della sintassi viene utilizzato per distinguere visivamente i campi evento (verde) dai gruppi di campi (blu).

## Valori predefiniti per i riferimenti di campo {#default-value}

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
>Il tipo di campo e il valore predefinito devono essere uguali. Ad esempio, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} non sarà valido perché il valore predefinito è un numero intero, mentre il valore previsto deve essere una stringa.

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

È possibile aggiungere qualsiasi tipo di espressione come valore predefinito. L’unico vincolo consiste nel fatto che l’espressione deve restituire il tipo di dati previsto. Quando si utilizza una funzione, è necessario incapsulare la funzione con ().

```
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.any.time, defaultValue : (now())} 
== date("2022-02-10T00:00:00Z")
```

## Riferimento a un campo nelle raccolte

Gli elementi definiti nelle raccolte sono referenziati utilizzando le funzioni specifiche `all`, `first` e `last`. Per ulteriori informazioni, consulta [questa pagina](../expression/collection-management-functions.md).

Esempio :

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## Riferimento a un campo definito in una mappa

### Funzione  di `entry`

Per recuperare un elemento in una mappa, utilizziamo la funzione di ingresso con una chiave specifica. Ad esempio, viene utilizzato quando si definisce la chiave di un evento, in base allo spazio dei nomi selezionato. Consulta Selezione dello spazio dei nomi . Per ulteriori informazioni, consulta [questa pagina](../event/selecting-the-namespace.md).

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

In questa espressione, otteniamo la voce per la chiave &quot;Email&quot; del campo &quot;IdentityMap&quot; di un evento. La voce &quot;Email&quot; è una raccolta da cui prendiamo l’&quot;id&quot; nel primo elemento utilizzando &quot;first()&quot;. Per ulteriori informazioni, consulta [questa pagina](../expression/collection-management-functions.md).

### Funzione  di `firstEntryKey`

Per recuperare la prima chiave di ingresso di una mappa, utilizza la `firstEntryKey` funzione .

Questo esempio mostra come recuperare il primo indirizzo e-mail degli abbonati a un elenco specifico:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

In questo esempio, l’elenco di sottoscrizioni è denominato `daily-email`. Gli indirizzi e-mail sono definiti come chiavi nel `subscribers` map, collegata alla mappa dell’elenco di abbonamenti.

### Funzione  di `keys`

Per recuperare tutte le chiavi di una mappa, utilizza le `keys` funzione .

Questo esempio mostra come recuperare, per un profilo specifico, tutti gli indirizzi e-mail associati agli abbonati di un elenco specifico:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## Valori dei parametri di un’origine dati (valori dinamici dell’origine dati)

Se selezioni un campo da un’origine dati esterna che richiede la chiamata di un parametro , viene visualizzata una nuova scheda a destra per consentirti di specificare questo parametro. Consulta [questa pagina](../expression/expressionadvanced.md).

Per casi d’uso più complessi, se desideri includere i parametri dell’origine dati nell’espressione principale, puoi definirne i valori utilizzando la parola chiave _params_. Un parametro può essere qualsiasi espressione valida anche da un&#39;altra origine dati che include anche un altro parametro.

>[!NOTE]
>
>Quando definisci i valori dei parametri nell’espressione, la scheda a destra scompare.

Utilizza la sintassi seguente:

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: nome esatto del primo parametro dall&#39;origine dati.
* **`<params-1-value>`**: il valore del primo parametro. Può essere qualsiasi espressione valida.

Esempio:

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
