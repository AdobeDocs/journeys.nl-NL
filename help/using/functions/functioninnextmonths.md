---
product: adobe campaign
solution: Journey Orchestration
title: inNextMonths
description: Meer informatie over de functie in NextMonths
feature: Reizen
role: Gegevensengineer
level: Ervaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inNextMonths {#inNextMonths}

Retourneert true als een bepaalde datum of dateTime zich tussen nu en nu + delta maanden bevindt.

## Categorie

Datum

## Functiesyntaxis

`inNextMonths(<dateTime>,<delta>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| datumtijd | dateTime |
| delta | integer |

## Handtekeningen en type geretourneerd

`inNextMonths(<dateTime>,<integer>)`

Retourneert een Booleaanse waarde.

## Voorbeelden

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

Retourneert true.
