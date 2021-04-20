---
product: adobe campaign
solution: Journey Orchestration
title: sum
description: Meer informatie over de functiesom
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 9%

---


# sum {#sum}

Retourneert de som van de waarden van een set expressies. Null-waarden worden genegeerd.

## Categorie

Samenvoeging

## Functiesyntaxis

`sum(<parameters>)`

## Parameters

* listInteger
* listDecimal
* duur
* integer
* decimaal

## Handtekeningen en geretourneerde typen

`sum(<listDecimal>)`

Retourneert een decimaal.

`sum(<listInteger>)`

Retourneert een geheel getal.

`sum(<integer>,<integer>)`

Retourneert een geheel getal.

`sum(<decimal>,<decimal>)`

Retourneert een decimaal.

## Voorbeelden

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

Retourneert 21.

`sum([10.5,null,8.1])`

Retourneert 18.6.
