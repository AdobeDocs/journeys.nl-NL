---
product: adobe campaign
title: substr
description: Meer informatie over de substr van de functie
feature: Journeys
role: Developer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 4%

---

# substr {#substr}

Retourneert de subtekenreeks van de tekenreeksexpressie tussen de beginindex en de eindindex. Als de eindindex niet is gedefinieerd, ligt deze tussen de beginindex en het einde.

## Categorie

String

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
