---
title: inNextYear
description: Meer informatie over de functie in NextYear
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1441402b50414443a6b6bb3087cf648cc74faa49

---


# inNextYear {#inNextYears}

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
