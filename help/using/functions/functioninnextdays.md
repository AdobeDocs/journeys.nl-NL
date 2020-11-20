---
product: adobe campaign
solution: Journey Orchestration
title: inNextDays
description: Meer informatie over de functie in NextDays
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextDays {#inNextDays}

Retourneert true als een bepaalde datum of dateTime zich tussen nu en nu + delta dagen bevindt.

## Categorie

Datum

## Functiesyntaxis

`inNextDays(<dateTime>,<delta>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| datumtijd | dateTime |
| delta | integer |

## Handtekeningen en type geretourneerd

`inNextDays(<dateTime>,<integer>)`

Retourneert een Booleaanse waarde.

## Voorbeelden

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Retourneert true.
