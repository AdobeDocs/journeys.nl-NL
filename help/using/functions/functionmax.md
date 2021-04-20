---
product: adobe campaign
solution: Journey Orchestration
title: max
description: Meer informatie over de functie max
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 5%

---

# max{#max}

Geeft als resultaat de maximale waarde tussen een reeks expressies, opgegeven als een lijst of twee expressies. Null-waarden worden genegeerd.

## Categorie

Samenvoeging

## Functiesyntaxis

`max(<parameter>)`

## Parameters

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* duur
* integer
* decimaal
* dateTime
* dateTimeOnly

## Handtekeningen en geretourneerde typen

`max(<listDuration>)`

Retourneert een duur.

`max(<listInteger>)`

Retourneert een duur.

`max(<listDateTimeOnly>)`

Retourneert een datetime zonder rekening te houden met tijdzone.

`max(<listDateTime>)`

Retourneert een datetime.

`max(<listDecimal>)`

Retourneert een decimaal.

`max(<decimal>,<decimal>)`

Retourneert een decimaal.

`max(<duration>,<duration>)`

Retourneert een duur.

`max(<dateTime>,<dateTime>)`

Retourneert een datetime.

`max(<dateTimeOnly>,<dateTimeOnly>)`

Retourneert een datetime zonder rekening te houden met tijdzone.

`max(<integer>,<integer>)`

Retourneert een geheel getal.

## Voorbeelden

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

Retourneert 10.

`max([10,null,8])`

Retourneert 10.
