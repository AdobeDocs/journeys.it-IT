---
title: toDateTime
description: Scopri la funzione toDateTime
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---

# toDateTime {#toDateTime}

Converte i parametri in un valore di data e ora, a seconda del tipo.

## Categoria

Conversione

## Sintassi funzione

`toDateTime(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|------------------|
| data e ora in formato ISO-8601 | string |
| id fuso orario | string |
| data e ora senza fuso orario | dateTimeOnly |
| valore intero di un&#39;epoch in millisecondi | integer |

>[!NOTE]
>
>L&#39;ID del fuso orario deve essere una costante stringa. Non può essere un riferimento a un campo né un&#39;espressione. Per ulteriori informazioni sui tipi di dati, fare riferimento a [](../expression/data-types.md).

## Firme e tipi restituiti

`toDateTime(<string>)`

`toDateTime(<dateTimeOnly>,<stringified time zone id>)`

`toDateTime(<integer>)`

Restituisce un **dataTime**.

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## Esempi

`toDateTime ("2016-08-18T23:17:59.123Z")`

Restituisce 2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("2016-08-18T23:17:59.123"),"UTC")`

Restituisce 2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

Restituisce 2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
