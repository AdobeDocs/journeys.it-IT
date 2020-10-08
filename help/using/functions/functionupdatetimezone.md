---
title: updateTimeZone
description: Scopri la funzione updateTimeZone
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
source-wordcount: '41'
ht-degree: 4%

---


# updateTimeZone {#updateTimeZone}

Restituisce una nuova ora di data, con un nuovo fuso orario nello stesso istante.

## Categoria

Data

## Sintassi delle funzioni

`updateTimeZone(<parameters>)`

## Parametri

* id fuso orario: string
* dateTime

## Firma e tipo restituito

`updateTimeZone(<dateTime>,<timeZone id>)`

Restituisce un valore datetime.

## Esempio

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Restituisce 2019-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
