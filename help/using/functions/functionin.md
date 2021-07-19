---
product: adobe campaign
title: in
description: Scopri la funzione in
feature: Percorsi
role: Data Engineer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 17%

---

# in {#in}

Controlla se il primo valore dell&#39;argomento si trova nell&#39;elenco. Il controllo viene eseguito tramite un valore Equal per ogni valore di argomento. Restituisce true se il valore dell&#39;argomento viene trovato, false in caso contrario.

Il tipo di `<expression>` deve corrispondere agli elementi dell’elenco. I tipi di elementi dell’elenco, come promemoria, devono corrispondere tra loro.

## Categoria

Elenco

## Sintassi della funzione

`in(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| Stringa | Stringa |
| Booleano | Booleano |
| Intero | Intero |
| Decimale | Decimale |
| Durata | Durata |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| Elenco | listString |
| Elenco | listBoolean |
| Elenco | listInteger |
| Elenco | listDecimal |
| Elenco | listDuration |
| Elenco | listDateTime |
| Elenco | listDateTimeOnly |

## Firma e tipo restituito

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

Restituisce un valore booleano.

## Esempio

`in(4,[4,5,3,4])`

Restituisce true.

`in(8,[4,5,3,4])`

Restituisce false.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
