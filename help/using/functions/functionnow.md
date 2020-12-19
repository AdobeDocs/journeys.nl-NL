---
product: adobe campaign
solution: Journey Orchestration
title: now
description: Meer informatie over de functie
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 10%

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