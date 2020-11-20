---
product: adobe campaign
solution: Journey Orchestration
title: inNextYears
description: Meer informatie over de functie in NextYear
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextYears {#inNextYears}

Retourneert true als een bepaalde datum of dateTime zich tussen nu en nu + delta jaar bevindt.

## Categorie

Datum

## Functiesyntaxis

`inNextYears(<dateTime>,<delta>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| datumtijd | dateTime |
| delta | integer |

## Handtekeningen en type geretourneerd

`inNextYears(<dateTime>,<integer>)`

Retourneert een Booleaanse waarde.

## Voorbeelden

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

Retourneert true.
