---
title: in
description: Scopri la funzione in
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 11%

---


# in {#in}

Controlla se il primo valore argomento è nell&#39;elenco. Il controllo viene eseguito tramite un valore Equal per ogni valore argomento. Restituisce true se il valore dell&#39;argomento viene trovato, false in caso contrario.

Il tipo di oggetto `<expression>` deve corrispondere agli elementi dell&#39;elenco. I tipi di elementi dell&#39;elenco, come promemoria, devono corrispondere l&#39;uno all&#39;altro.

## Categoria

Elenco

## Sintassi delle funzioni

`in(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| Stringa | Stringa |
| Booleano | Booleano |
| Integer | Integer |
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
