---
title: nu
description: Meer weten over de functie?
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
source-git-commit: a0db4d65218861b71d35f83ccf2d15e25a1597e8

---


# nu {#now}

Keert de huidige datum in het formaat van de datumtijd terug. Voor meer informatie over gegevenstypes, verwijs naar [](../expression/data-types.md).

## Categorie

Datum

## Functiesyntaxis

`now(<parameter>)`

## Parameters

| Parameter | Beschrijving |
|--- |--- |
| touwtje |  |

## Handtekeningen en teruggestuurd type

`now()`

`now("<timeZone id>")`

Keert een dateTime terug.

## Voorbeelden

`now()`

Geeft 2019-06-03T06:30Z.

`toString(now())`

Geeft &quot;2019-06-03T06:30Z&quot; terug

`now("Europe/Paris")`

Keert 2019-06-03T08:30+02:00 terug.