---
product: adobe campaign
title: avg
description: Meer informatie over de functie avg
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 12%

---

# avg {#avg}

Geeft als resultaat de gemiddelde waarde tussen een reeks expressies, opgegeven als een lijst of twee expressies. Null-waarden worden genegeerd.


## Categorie

Samenvoeging

## Functiesyntaxis

`avg(<parameter>)`

## Parameters

Ondersteunde typen:

* listInteger
* listDecimal
* decimaal
* integer

## Handtekeningen en type geretourneerd

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

Retourneert een decimaal.

## Voorbeelden

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

Retourneert 7.0.

`avg(10.2, 3)`

Retourneert 6.6.
