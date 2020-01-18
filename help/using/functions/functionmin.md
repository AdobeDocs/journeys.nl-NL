---
title: min
description: Meer informatie over de functie min
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

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
