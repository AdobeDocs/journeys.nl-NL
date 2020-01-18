---
title: now
description: Meer informatie over de functie
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
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003

---


# now {#now}

Retourneert de huidige datum in de datumtijdnotatie. Raadpleeg [](../expression/data-types.md)voor meer informatie over gegevenstypen.

## Categorie

Datum

## Functiesyntaxis

`now(<parameter>)`

## Parameters

| Parameter | Beschrijving |
|--- |--- |
|  string |  |

## Handtekeningen en type geretourneerd

`now()`

`"now(<timeZone id>")`

Retourneert een dateTime.

## Voorbeelden

`now()`

Retourneert 2019-06-03T06:30Z.

`toString(now())`

Retourneert &quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

Retourneert 2019-06-03T08:30+02:00.