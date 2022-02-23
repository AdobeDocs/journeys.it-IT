---
product: adobe campaign
title: replace
description: Informazioni sulla sostituzione della funzione
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

Sostituisce la prima occorrenza che corrisponde alla stringa di destinazione dalla stringa di sostituzione nella stringa di base.

La sostituzione procede dall’inizio della stringa alla fine, ad esempio sostituendo &quot;aa&quot; con &quot;b&quot; nella stringa &quot;aaa&quot; si otterrà &quot;ba&quot; invece di &quot;ab&quot;.

## Categoria

Stringa

## Sintassi della funzione

`replace(<parameters>)`

## Parametri

| Parametro | Tipo |
|-----------|--------------|
| base | stringa |
| target | string (RegExp) |
| sostituzione | stringa |

## Firma e tipo restituito

`replace(<base>,<target>,<replacement>)`

Restituisce una stringa.

## Esempio 1

`replace("Hello World", "l", "x")`

Restituisce &quot;Hexlo World&quot;.

## Esempio 2 {#example_2}

Poiché il parametro di destinazione è un RegExp, a seconda della stringa che desideri sostituire, potrebbe essere necessario applicare l’escape di alcuni caratteri. Ecco un esempio:

* stringa da valutare: `|OFFER_A|OFFER_B`
* fornito da un attributo di profilo `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* Stringa da sostituire: `|OFFER_A`
* Stringa sostituita da: `''`
* È necessario aggiungere `\\` prima del `|` carattere.

L&#39;espressione è:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

La stringa restituita è: `|OFFER_B`

Puoi anche creare la stringa da sostituire da un dato attributo:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
