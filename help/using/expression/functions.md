---
product: adobe campaign
title: Funzioni
description: Informazioni sulle funzioni
feature: Journeys
role: Developer
level: Experienced
exl-id: b514d2e9-1444-46d5-a1ac-3591e62807c1
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 79%
---
# Funzioni {#concept_p1r_qj5_dgb}


>[!CAUTION]
>
>**Stai cercando Adobe Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai precedenti materiali su Journey Orchestration, che è stato sostituito da Journey Optimizer. In caso di domande sull’accesso a Journey Orchestration o Journey Optimizer, contatta il team del tuo account._


Una funzione può avere firme diverse (un diverso set di parametri ordinati). Una firma di funzione può avere espressioni 0-N come parametri ordinati.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

Ogni funzione ha un tipo restituito specifico.

Elenco delle funzioni supportate.

## Funzioni principali

| Categoria | Funzione |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| Aggregazione | [avg](../functions/functionavg.md) |
| Aggregazione | [count](../functions/functioncount.md) |
| Aggregazione | [countOnlyNull](../functions/functioncountonlynull.md) |
| Aggregazione | [countWithNull](../functions/functioncountwithnull.md) |
| Aggregazione | [distinctCount](../functions/functiondistinctcount.md) |
| Aggregazione | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| Aggregazione | [max](../functions/functionmax.md) |
| Aggregazione | [min](../functions/functionmin.md) |
| Aggregazione | [sum](../functions/functionsum.md) |
| Conversione | [toBool](../functions/functiontobool.md) |
| Conversione | [toDateOnly](../functions/functiontodateonly.md) |
| Conversione | [toDateTime](../functions/functiontodatetime.md) |
| Conversione | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| Conversione | [toDecimal](../functions/functiontodecimal.md) |
| Conversione | [toDuration](../functions/functiontoduration.md) |
| Conversione | [toInteger](../functions/functiontointeger.md) |
| Conversione | [toString](../functions/functiontostring.md) |
| Data | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| Data | [inLastDays](../functions/functioninlastdays.md) |
| Data | [inLastHours](../functions/functioninlasthours.md) |
| Data | [inLastMonths](../functions/functioninlastmonths.md) |
| Data | [inLastYears](../functions/functioninlastyears.md) |
| Data | [inNextDays](../functions/functioninnextdays.md) |
| Data | [inNextHours](../functions/functioninnexthours.md) |
| Data | [inNextMonths](../functions/functioninnextmonths.md) |
| Data | [inNextYears](../functions/functioninnextyears.md) |
| Data | [now](../functions/functionnow.md) |
| Data | [nowWithDelta](../functions/functionnowwithdelta.md) |
| Data | [setHours](../functions/functionsethours.md) |
| Data | [setDays](../functions/functionsetdays.md) |
| Data | [updateTimeZone](../functions/functionupdatetimezone.md) |
| Elenco | [distinct](../functions/functiondistinct.md) |
| Elenco | [distinctWithNull](../functions/functiondistinctwithnull.md) |
| Elenco | [filtro](../functions/functionfilter.md) |
| Elenco | [getListItem](../functions/functiongetlistitem.md) |
| Elenco | [in](../functions/functionin.md) |
| Elenco | [intersezione](../functions/functionintersect.md) |
| Elenco | [listSize](../functions/functionlistsize.md) |
| Elenco | [serializeList](../functions/functionserializelist.md) |
| Elenco | [sort](../functions/functionsort.md) |
| Matematica | [random](../functions/functionrandom.md) |
| Matematica | [round](../functions/functionround.md) |
| Stringa | [concat](../functions/functionconcat.md) |
| Stringa | [contain](../functions/functioncontain.md) |
| Stringa | [containIgnoreCase](../functions/functioncontainwithignorecase.md) |
| Stringa | [endWith](../functions/functionendwith.md) |
| Stringa | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| Stringa | [equalIgnoreCase](../functions/functionequalignorecase.md) |
| Stringa | [indexOf](../functions/functionindexof.md) |
| Stringa | [isEmpty](../functions/functionisempty.md) |
| Stringa | [isNotEmpty](../functions/functionisnotempty.md) |
| Stringa | [lastIndexOf](../functions/functionlastindexof.md) |
| Stringa | [length](../functions/functionlength.md) |
| Stringa | [Lower](../functions/functionlower.md) |
| Stringa | [matchRegExp](../functions/functionmatchregexp.md) |
| Stringa | [notEqualIgnoreCase](../functions/functionnotequalignorecase.md) |
| Stringa | [replace](../functions/functionreplace.md) |
| Stringa | [replaceAll](../functions/functionreplaceall.md) |
| Stringa | [startWith](../functions/functionstartwith.md) |
| Stringa | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| Stringa | [substr](../functions/functionsubstr.md) |
| Stringa | [trim](../functions/functiontrim.md) |
| Stringa | [upper](../functions/functionupper.md) |
| Stringa | [uuid](../functions/functionuuid.md) |
