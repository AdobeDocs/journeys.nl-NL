---
product: adobe campaign
solution: Journey Orchestration
title: min
description: Meer informatie over de functie min
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

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
