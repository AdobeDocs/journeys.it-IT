---
product: adobe campaign
title: Funzioni
description: Scopri sulle funzioni
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b514d2e9-1444-46d5-a1ac-3591e62807c1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 57%

---

# Funzioni {#concept_p1r_qj5_dgb}


>[!CAUTION]
>
>**Cerchi Adobe Systems Journey Optimizer**? Fai clic [qui](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/ajo-home){target="_blank"} per la documentazione di Journey Optimizer.
>
>
>_Questa documentazione fa riferimento ai materiali Journey Orchestration legacy sostituiti da Journey Optimizer. Contatta il tuo team account se hai domande sulle accesso a Journey Orchestration o Journey Optimizer._


Una funzione può avere firme diverse (un diverso insieme di parametri ordinati). Una firma di funzione può avere espressioni 0-N come parametri ordinati.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

Ogni funzione ha un tipo restituito specifico.

Di seguito è riportato l&#39;elenco delle funzioni supportate.

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
| Elenco | [intersecare](../functions/functionintersect.md) |
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
