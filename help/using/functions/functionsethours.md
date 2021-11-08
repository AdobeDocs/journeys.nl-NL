---
product: adobe campaign
title: setHours
description: Meer informatie over de functie setHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 6%

---

# setHours {#setHours}

Hiermee stelt u alleen de uren van een datumtijd of datumtijd in. Als u bijvoorbeeld tot een bepaald uur wilt wachten, kunt u het uur forceren.

## Categorie

Datum

## Functiesyntaxis

`setHours(<parameter>)`

## Parameters

| Parameter | Type |
|--- |--- |
| datumtijd | dateTime |
| datumtijd zonder tijdzone te overwegen | dateTimeOnly |
| uren | integer |

## Handtekeningen en type geretourneerd

`setHours(<dateTime>,<hours>)`

Retourneert een datetime.

`setHours(<dateTimeOnly>,<hours>)`

Retourneert een datetime zonder rekening te houden met tijdzone.

## Voorbeelden

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retourneert 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Keert morgen om 8:XY PM terug, die XY de notulen op het ogenblik van de huidige tijdevaluatie zijn. Als de evaluatie om 2:45 AM gebeurt, zal de teruggekeerde tijd 8:45 PM zijn.
