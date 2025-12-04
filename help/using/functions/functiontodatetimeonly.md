---
product: adobe campaign
title: toDateTimeOnly
description: Meer informatie over de functie toDateTime
feature: Journeys
role: Developer
level: Experienced
exl-id: b19adbd0-8449-4bd4-bc4d-f1f305f87cb0
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 8%

---

# toDateTimeOnly{#toDateTimeOnly}

Zet een argumentwaarde in een waarde van de datumtijd slechts om.

## Categorie

Conversie

## Functiesyntaxis

`toDateTimeOnly(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| datumtijd in de notatie ISO-8601 of &quot;JJJ-MM-DD&quot; (XDM-datumnotatie) | string |
| datumtijd | dateTime |

## Handtekeningen en geretourneerde typen

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Retourneer een datetime zonder rekening te houden met tijdzone.

## Voorbeelden

`toDateTimeOnly ("2016-08-18")`

keert dateTime terug die 2016-08-18T00 :00: 00.000 vertegenwoordigt

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
