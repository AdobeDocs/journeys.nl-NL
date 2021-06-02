---
product: adobe campaign
title: endWithIgnoreCase
description: Meer informatie over de functie endWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 8%

---

# endWithIgnoreCase {#endWithIgnoreCase}

Controleert of de tekenreeks van het eerste argument eindigt met een specifieke tekenreeks (tekenreeks van het tweede argument), waarbij geen rekening wordt gehouden met het geval.

## Categorie

Tekenreeks

## Functiesyntaxis

`endWithIgnoreCase(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| string | string |
| achtervoegsel | string |

## Handtekening en type geretourneerd

`endWithIgnoreCase(<string>,<string>)`

Retourneert een Booleaanse waarde.

## Voorbeeld

`endWithIgnoreCase("rowing is great', "AT")`

Retourneert true.
