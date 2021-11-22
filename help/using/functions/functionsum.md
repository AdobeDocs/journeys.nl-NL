---
product: adobe campaign
title: sum
description: Meer informatie over de functiesom
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 11%

---

# som {#sum}

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
