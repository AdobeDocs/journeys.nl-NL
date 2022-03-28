---
product: adobe campaign
title: toDateOnly
description: Meer informatie over de functie toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
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
