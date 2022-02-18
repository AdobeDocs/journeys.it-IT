---
product: adobe campaign
title: intersect
description: Scopri l’intersezione della funzione
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---

# intersecare{#intersect}

Restituisce i valori comuni nei due elenchi di input. Se uno dei due elenchi è nullo, restituisce un elenco vuoto.

## Categoria

Elenco

## Sintassi della funzione

`intersect(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| elenco 1 | elenco |
| elenco 2 | elenco |

## Firme e tipi restituiti

`intersect(listString,listString)`: listString
`intersect(listDecimal,listDecimal)`: listDecimal
`intersect(listInteger,listInteger)`: listInteger
`intersect(listDateTime,listDateTime)`: listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`: listDateOnly
`intersect(listDuration,listDuration)`: listDuration
`intersect(listBoolean,listBoolean)`: listBoolean

Restituisce un elenco.

## Esempi

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Restituisce [&quot;sport&quot;, &quot;notizie&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Restituisce elementi comuni tra gli attributi del profilo e un elenco di categorie specificato.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

Restituisce elementi comuni tra gli attributi del profilo e il campo evento specificato.
