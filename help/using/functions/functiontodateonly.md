---
product: adobe campaign
title: toDateOnly
description: Meer informatie over de functie toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5e2af021f1c82063fcc0d4e4b5edf13c57cc6c72
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 9%

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