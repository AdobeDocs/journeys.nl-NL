---
title: setHours
description: Meer informatie over de functie setHours
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

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

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Retourneert 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Retourneert morgen om 8 uur.
