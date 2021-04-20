---
product: adobe campaign
solution: Journey Orchestration
title: Functies
description: Meer informatie over functies
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 71%

---


# Functies {#concept_p1r_qj5_dgb}

Een functie kan verschillende handtekeningen hebben (een andere set geordende parameters). Een functiehandtekening kan 0-N-expressies hebben als geordende parameters.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

Elke functie heeft een specifiek type dat wordt geretourneerd.

Hier volgt een lijst met ondersteunde functies.

## Belangrijkste functies

| Categorie | -functie |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| Samenvoeging | [avg](../functions/functionavg.md) |
| Samenvoeging | [count](../functions/functioncount.md) |
| Samenvoeging | [countOnlyNull](../functions/functioncountonlynull.md) |
| Samenvoeging | [countWithNull](../functions/functioncountwithnull.md) |
| Samenvoeging | [distinctCount](../functions/functiondistinctcount.md) |
| Samenvoeging | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| Samenvoeging | [max](../functions/functionmax.md) |
| Samenvoeging | [min](../functions/functionmin.md) |
| Samenvoeging | [sum](../functions/functionsum.md) |
| Conversie | [toBool](../functions/functiontobool.md) |
| Conversie | [toDateTime](../functions/functiontodatetime.md) |
| Conversie | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| Conversie | [toDecimal](../functions/functiontodecimal.md) |
| Conversie | [toDuration](../functions/functiontoduration.md) |
| Conversie | [toInteger](../functions/functiontointeger.md) |
| Conversie | [toString](../functions/functiontostring.md) |
| Datum | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| Datum | [inLastDays](../functions/functioninlastdays.md) |
| Datum | [inLastHours](../functions/functioninlasthours.md) |
| Datum | [inLastMonths](../functions/functioninlastmonths.md) |
| Datum | [inLastYears](../functions/functioninlastyears.md) |
| Datum | [inNextDays](../functions/functioninnextdays.md) |
| Datum | [inNextHours](../functions/functioninnexthours.md) |
| Datum | [inNextMonths](../functions/functioninnextmonths.md) |
| Datum | [inNextYears](../functions/functioninnextyears.md) |
| Datum | [now](../functions/functionnow.md) |
| Datum | [nowWithDelta](../functions/functionnowwithdelta.md) |
| Datum | [setHours](../functions/functionsethours.md) |
| Datum | [setDays](../functions/functionsetdays.md) |
| Lijst | [distinct](../functions/functiondistinct.md) |
| Lijst | [differentCount](../functions/functiondistinctcount.md) |
| Lijst | [in](../functions/functionin.md) |
| Lijst | [listSize](../functions/functionlistsize.md) |
| Lijst | [serializeList](../functions/functionserializelist.md) |
| Lijst | [sort](../functions/functionsort.md) |
| Wiskundig | [random](../functions/functionrandom.md) |
| Wiskundig | [round](../functions/functionround.md) |
| Tekenreeks | [concat](../functions/functionconcat.md) |
| Tekenreeks | [contain](../functions/functioncontain.md) |
| Tekenreeks | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| Tekenreeks | [endWith](../functions/functionendwith.md) |
| Tekenreeks | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| Tekenreeks | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| Tekenreeks | [indexOf](../functions/functionindexof.md) |
| Tekenreeks | [isEmpty](../functions/functionisempty.md) |
| Tekenreeks | [isNotEmpty](../functions/functionisnotempty.md) |
| Tekenreeks | [lastIndexOf](../functions/functionlastindexof.md) |
| Tekenreeks | [length](../functions/functionlength.md) |
| Tekenreeks | [lower](../functions/functionlower.md) |
| Tekenreeks | [matchRegExp](../functions/functionmatchregexp.md) |
| Tekenreeks | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| Tekenreeks | [replace](../functions/functionreplace.md) |
| Tekenreeks | [replaceAll](../functions/functionreplaceall.md) |
| Tekenreeks | [startWith](../functions/functionstartwith.md) |
| Tekenreeks | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| Tekenreeks | [substr](../functions/functionsubstr.md) |
| Tekenreeks | [trim](../functions/functiontrim.md) |
| Tekenreeks | [upper](../functions/functionupper.md) |
| Tekenreeks | [uuid](../functions/functionuuid.md) |