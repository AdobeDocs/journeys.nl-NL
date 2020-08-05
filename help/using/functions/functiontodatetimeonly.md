---
title: toDateTimeOnly
description: Meer informatie over de functie toDateTime
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 2%

---


# toDateTimeOnly{#toDateTimeOnly}

Zet een argumentwaarde in een waarde van de datumtijd slechts om.

## Categorie

Conversie

## Functiesyntaxis

`toDateTimeOnly(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| date time without time zone in ISO-8601 format | string |
| dateTime | dateTime |

## Handtekeningen en geretourneerde typen

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Retourneer een datetime zonder rekening te houden met tijdzone.

## Voorbeelden

`toDateTimeOnly ("2016-08-18T23:17:59.123")`

Retourneert 2016-08-18T23:17:59.123.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
