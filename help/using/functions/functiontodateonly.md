---
product: adobe campaign
title: toDateOnly
description: Meer informatie over de functie toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 13%

---

# toDateOnly{#toDateOnly}

Hiermee wordt een argumentwaarde omgezet in een waarde met alleen de datum.

## Categorie

Conversie

## Functiesyntaxis

`toDateOnly(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| datum in de notatie ISO-8601 of &quot;JJJ-MM-DD&quot; (XDM-datumnotatie) | string |
| date | date |

## Handtekeningen en geretourneerde typen

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Retourneer een datetime zonder rekening te houden met tijdzone.

## Voorbeelden

`toDateOnly("2016-08-18")`

retourneert een dateOnly-object dat 2016-08-18 vertegenwoordigt.
