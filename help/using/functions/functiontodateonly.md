---
product: adobe campaign
title: toDateOnly
description: Meer informatie over de functie toDateOnly
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
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
