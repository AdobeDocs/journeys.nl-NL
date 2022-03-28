---
product: adobe campaign
title: updateTimeZone
description: Meer informatie over de functie updateTimeZone
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2ce60ed2-161a-4b98-9694-eb47cc0e04a9
source-git-commit: d5531d0aad22f33da2cc5612cc289c600411fd8c
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 11%

---

# updateTimeZone {#updateTimeZone}

Retourneert een nieuwe datumtijd met een nieuwe tijdzone op hetzelfde moment.

## Categorie

Datum

## Functiesyntaxis

`updateTimeZone(<parameters>)`

## Parameters

* tijdzone-id: string
* dateTime

## Handtekening en type geretourneerd

`updateTimeZone(<dateTime>,<timeZone id>)`

Retourneert een datetime.

## Voorbeelden

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Retourneert 2019-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

Als de waarde van het tijdstempelveld gelijk is aan `2021-11-16T16:55:12.939318+01:00`, dan retourneert de functie `2021-11-17T02:55:12.942115+11:00`.
