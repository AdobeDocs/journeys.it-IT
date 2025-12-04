---
product: adobe campaign
title: intersect
description: Scopri l’intersezione della funzione
feature: Journeys
role: Developer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 12%

---

# intersect{#intersect}

Restituisce i valori comuni nei due elenchi di input. Se uno dei due elenchi è nullo, restituisce un elenco vuoto.

## Categoria

Elenco

## Sintassi della funzione

`intersect(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| elenco 1 | list |
| elenco 2 | list |

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

Restituisce [&quot;sport&quot;, &quot;news&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Restituisce elementi comuni tra gli attributi del profilo e un elenco specifico di categorie.

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

Restituisce elementi comuni tra gli attributi del profilo e il campo evento specificato.
