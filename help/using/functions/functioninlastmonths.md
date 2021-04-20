---
product: adobe campaign
solution: Journey Orchestration
title: inLastMonths
description: Meer informatie over de functie in LastMonths
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inLastMonths {#inLastMonths}

Retourneert true als een bepaalde datum of dateTime zich tussen nu en nu bevindt - delta-maanden.

## Categorie

Datum

## Functiesyntaxis

`inLastMonths(<dateTime>,<delta>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| datumtijd | dateTime |
| delta | integer |

## Handtekeningen en type geretourneerd

`inLastMonths(<dateTime>,<integer>)`

Retourneert een Booleaanse waarde.

## Voorbeelden

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4))`

Retourneert true.
