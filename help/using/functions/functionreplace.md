---
product: adobe campaign
title: replace
description: Scopri la funzione Sostituisci
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 10%

---

# replace {#replace}

Sostituisce la prima occorrenza corrispondente alla stringa di destinazione con la stringa di sostituzione nella stringa di base.

La sostituzione procede dall&#39;inizio della stringa alla fine, ad esempio, sostituendo &quot;aa&quot; con &quot;b&quot; nella stringa &quot;aaa&quot; si otterrà &quot;ba&quot; invece di &quot;ab&quot;.

## Categoria

Stringa

## Sintassi della funzione

`replace(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|--------------|
| base | string |
| target | stringa (RegExp) |
| sostituzione | string |

## Firma e tipo restituito

`replace(<base>,<target>,<replacement>)`

Restituisce una stringa.

## Esempio 1

`replace("Hello World", "l", "x")`

Restituisce &quot;Hexlo World&quot;.

## Esempio 2 {#example_2}

Poiché il parametro di destinazione è un RegExp, a seconda della stringa che si desidera sostituire, potrebbe essere necessario eseguire l&#39;escape di alcuni caratteri. Ecco un esempio:

* stringa da valutare: `|OFFER_A|OFFER_B`
* fornito da un attributo di profilo `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* Stringa da sostituire: `|OFFER_A`
* Stringa sostituita da: `''`
* Devi aggiungere `\\` prima del `|` carattere.

L’espressione è:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

La stringa restituita è: `|OFFER_B`

Puoi anche creare la stringa da sostituire da un dato attributo:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
