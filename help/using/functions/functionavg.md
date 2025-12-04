---
product: adobe campaign
title: avg
description: Meer informatie over de functie avg
feature: Journeys
role: Developer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 7%

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
