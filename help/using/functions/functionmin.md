---
product: adobe campaign
title: min
description: Meer informatie over de functie min
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 6%

---

# min {#min}

Geeft als resultaat de minimumwaarde tussen een reeks expressies, opgegeven als een lijst of twee expressies. Null-waarden worden genegeerd.

## Categorie

Samenvoeging

## Functiesyntaxis

`min(<parameters>)`

## Parameters

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* listDateOnly
* duur
* integer
* decimaal
* dateTime
* dateTimeOnly

## Handtekeningen en geretourneerde typen

`min(<listDuration>)`

Retourneert een duur.

`min(<listInteger>)`

Retourneert een duur.

`min(<listDateTimeOnly>)`

Retourneert een datetime zonder rekening te houden met tijdzone.

`min(<listDateTime>)`

Retourneert een datetime.

`min(<listDateOnly>)`

Retourneert een datum.

`min(<listDecimal>)`

Retourneert een decimaal.

`min(<decimal>,<decimal>)`

Retourneert een decimaal.

`min(<duration>,<duration>)`

Retourneert een duur.

`min(<dateTime>,<dateTime>)`

Retourneert een datetime.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Retourneert een datetime zonder rekening te houden met tijdzone.

`min(<integer>,<integer>)`

Retourneert een geheel getal.

## Voorbeelden

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

Retourneert 3.

`min([10,null,8])`

Retourneert 8.
