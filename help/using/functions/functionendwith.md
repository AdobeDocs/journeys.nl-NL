---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: Meer informatie over de functie endWith
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

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
