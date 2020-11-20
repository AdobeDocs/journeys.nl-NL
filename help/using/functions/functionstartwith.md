---
product: adobe campaign
solution: Journey Orchestration
title: startWith
description: Meer informatie over de functie startWith
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---


# startWith {#startWith}

Retourneert true als de tweede parameter een voorvoegsel van de eerste is.

## Categorie

Tekenreeks

## Functiesyntaxis

`startWith(<parameters>)`

## Parameters

| Parameter | Type |
|-------------|--------|
| string | string |
| prefix | string |

## Handtekening en type geretourneerd

`startWith(<string>,<string>)`

Retourneer een booleaanse waarde.

## Voorbeeld

`startWith("Hello World", "Hello")`

Retourneert true.

`startWith("Hello World", "World")`

Retourneert false.
