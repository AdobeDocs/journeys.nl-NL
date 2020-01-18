---
title: endWith
description: Meer informatie over de functie endWith
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
source-git-commit: a844adc1a073aebfb7fd8a719e52f305079260b7

---


# endWith {#endWith}

Retourneert true als de tweede parameter een achtervoegsel van de eerste parameter is.

## Categorie

String

## Functiesyntaxis

`endWith(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
|  string |  string |
| achtervoegsel |  string |

## Handtekening en type geretourneerd

`endWith(<string>,<string>)`

Retourneert een Booleaanse waarde.

## Voorbeeld

`endWith("Hello World", "World")`

Retourneert true.

`endWith("Hello World", "Hello")`

Retourneert false.
