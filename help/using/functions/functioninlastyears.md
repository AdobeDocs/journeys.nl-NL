---
product: adobe campaign
title: inLastYears
description: Meer informatie over de functie in LastYear
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

---

# inLastYear {#inLastYears}

Retourneert true als een bepaalde datum of dateTime zich tussen nu en nu bevindt - delta-jaren.

## Categorie

Datum

## Functiesyntaxis

`inLastYears(<dateTime>,<delta>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| datumtijd | dateTime |
| delta | integer |

## Handtekeningen en type geretourneerd

`inLastYears(<dateTime>,<integer>)`

Retourneert een Booleaanse waarde.

## Voorbeelden

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retourneert true.
