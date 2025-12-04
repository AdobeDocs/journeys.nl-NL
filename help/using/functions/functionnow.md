---
product: adobe campaign
title: now
description: Meer informatie over de functie
feature: Journeys
role: Developer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 9%

---

# now {#now}

Retourneert de huidige datum in de datumtijdnotatie. Voor meer informatie over gegevenstypes, verwijs naar [&#x200B; deze pagina &#x200B;](../expression/data-types.md).

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

Keert 2019-06-03T06 :30Z terug.

`toString(now())`

Retourneert &quot;2019-06-03T06 :30Z&quot;

`now("Europe/Paris")`

Keert 2019-06-03T08 :30+02 :00 terug.
