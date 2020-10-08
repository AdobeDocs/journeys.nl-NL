---
title: substr
description: Meer informatie over de substr van de functie
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 6%

---


# substr {#substr}

Retourneert de subtekenreeks van de tekenreeksexpressie tussen de beginindex en de eindindex. Als de eindindex niet is gedefinieerd, ligt deze tussen de beginindex en het einde.

## Categorie

Tekenreeks

## Functiesyntaxis

`substr(<parameters>)`

## Parameters

| Parameter | type |
|-------------|----------|
| string | string |
| beginIndex | integer |
| endIndex | integer |

## Handtekening en type geretourneerd

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Retourneer een tekenreeks.

## Voorbeeld

`substr("Hello World",6)`

Retourneert &quot;World&quot;.

`substr("Hello World", 0, 5)`

Retourneert &quot;Hello&quot;.