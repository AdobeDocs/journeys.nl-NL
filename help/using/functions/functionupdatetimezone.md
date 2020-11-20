---
product: adobe campaign
solution: Journey Orchestration
title: updateTimeZone
description: Meer informatie over de functie updateTimeZone
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 4%

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

## Voorbeeld

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Retourneert 2019-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
