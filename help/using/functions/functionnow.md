---
product: adobe campaign
title: now
description: Meer informatie over de functie
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 16%

---

# now {#now}

Retourneert de huidige datum in de datumtijdnotatie. Raadpleeg [deze pagina](../expression/data-types.md) voor meer informatie over gegevenstypen.

## Categorie

Datum

## Functiesyntaxis

`now(<parameter>)`

## Parameters

| Parameter | Beschrijving |
|--- |--- |
| string |  |

## Handtekeningen en type geretourneerd

`now()`

`now("<timeZone id>")`

Retourneert een dateTime.

## Voorbeelden

`now()`

Retourneert 2019-06-03T06:30Z.

`toString(now())`

Retourneert &quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

Retourneert 2019-06-03T08:30+02:00.
