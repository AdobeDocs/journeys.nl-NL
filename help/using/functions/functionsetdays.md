---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: Meer informatie over de functie setDays
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 6%

---


# setDays {#setDays}

Hiermee stelt u alleen de dag van een datumtijd of datumtijd in. Als u bijvoorbeeld wilt wachten tot een bepaalde dag van de maand, kunt u de dag forceren.

## Categorie

Datum

## Functiesyntaxis

`setDays(<parameter>)`

## Parameters

| Parameter | Type |
|--- |--- |
| datumtijd | dateTime |
| datumtijd zonder tijdzone te overwegen | dateTimeOnly |
| dagen | integer |

## Handtekeningen en type geretourneerd

`setDays(<dateTime>,<days>)`

Retourneert een datetime.

`setDays(<dateTimeOnly>,<days>)`

Retourneert een datetime zonder rekening te houden met tijdzone.

## Voorbeelden

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Retourneert 2010-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
