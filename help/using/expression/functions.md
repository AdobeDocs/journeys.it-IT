---
product: adobe campaign
solution: Journey Orchestration
title: Funzioni
description: Informazioni sulle funzioni
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 73%

---


# Funzioni {#concept_p1r_qj5_dgb}

Una funzione può avere firme diverse (un insieme diverso di parametri ordinati). Una firma di funzione può avere espressioni da 0 a 0 come parametri ordinati.

`<function name>`(`<expression as param 1>`,  `<expression as param 2>`, ... ,`<expression as param N>`)

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
| Elenco | [distinct](../functions/functiondistinct.md) |
| Elenco | [separateCount](../functions/functiondistinctcount.md) |
| Elenco | [in](../functions/functionin.md) |
| Elenco | [listSize](../functions/functionlistsize.md) |
| Elenco | [serializeList](../functions/functionserializelist.md) |
| Elenco | [sort](../functions/functionsort.md) |
| Matematica | [random](../functions/functionrandom.md) |
| Matematica | [round](../functions/functionround.md) |
| Stringa | [concat](../functions/functionconcat.md) |
| Stringa | [contain](../functions/functioncontain.md) |
| Stringa | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| Stringa | [endWith](../functions/functionendwith.md) |
| Stringa | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| Stringa | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| Stringa | [indexOf](../functions/functionindexof.md) |
| Stringa | [isEmpty](../functions/functionisempty.md) |
| Stringa | [isNotEmpty](../functions/functionisnotempty.md) |
| Stringa | [lastIndexOf](../functions/functionlastindexof.md) |
| Stringa | [length](../functions/functionlength.md) |
| Stringa | [Lower](../functions/functionlower.md) |
| Stringa | [matchRegExp](../functions/functionmatchregexp.md) |
| Stringa | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| Stringa | [replace](../functions/functionreplace.md) |
| Stringa | [replaceAll](../functions/functionreplaceall.md) |
| Stringa | [startWith](../functions/functionstartwith.md) |
| Stringa | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| Stringa | [substr](../functions/functionsubstr.md) |
| Stringa | [trim](../functions/functiontrim.md) |
| Stringa | [top](../functions/functionupper.md) |
| Stringa | [uuid](../functions/functionuuid.md) |