---
product: adobe campaign
title: updateTimeZone
description: Scopri la funzione updateTimeZone
feature: Journeys
role: Developer
level: Experienced
exl-id: 2ce60ed2-161a-4b98-9694-eb47cc0e04a9
source-git-commit: 58514d6757f9705f5baa71cfbbe0bdfe65c8e16c
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 10%

---

# updateTimeZone {#updateTimeZone}

Restituisce una nuova data e ora, con un nuovo fuso orario nello stesso istante.

## Categoria

Data

## Sintassi della funzione

`updateTimeZone(<parameters>)`

## Parametri

* id fuso orario: stringa
* dateTime

## Firma e tipo restituito

`updateTimeZone(<dateTime>,<timeZone id>)`

Restituisce un valore datetime.

## Esempi

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Restituisce 2019-08-28T17:15:30.123+02:00.

<!--
`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".
-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

Se il valore del campo timestamp è `2021-11-16T16:55:12.939318+01:00`, la funzione restituisce `2021-11-17T02:55:12.942115+11:00`.
