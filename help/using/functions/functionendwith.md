---
product: adobe campaign
title: endWith
description: Meer informatie over de functie endWith
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 13%

---

# endWith {#endWith}

Retourneert true als de tweede parameter een achtervoegsel van de eerste parameter is.

## Categorie

Tekenreeks

## Functiesyntaxis

`endWith(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| string | string |
| achtervoegsel | string |

## Handtekening en type geretourneerd

`endWith(<string>,<string>)`

Retourneert een Booleaanse waarde.

## Voorbeeld

`endWith("Hello World", "World")`

Retourneert true.

`endWith("Hello World", "Hello")`

Retourneert false.
