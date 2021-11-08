---
product: adobe campaign
title: inLastMonths
description: Meer informatie over de functie in LastMonths
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 15%

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

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retourneert true.
