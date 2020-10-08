---
title: toBool
description: Meer informatie over de functie toBool
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
source-wordcount: '74'
ht-degree: 5%

---


# toBool {#toBool}

Zet een argumentwaarde in een booleaanse waarde om, afhankelijk van het type.

* Van tekenreeks: probeer de tekenreekswaarde om te zetten als een booleaanse waarde, van &quot;true&quot; als de tekenreekswaarde &quot;true&quot; is, anders false
* Uit numeriek: true als de numerieke waarde niet gelijk is aan 0, false in andere gevallen

## Categorie

Conversie

## Functiesyntaxis

`toBool(<parameter>)`

## Parameters

* decimaal
* boolean
* string
* integer

## Handtekeningen en geretourneerde typen

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Retourneer een booleaanse waarde.

## Voorbeelden

`toBool("true")`

`toBool(1)`

Retourneert true.

`toBool("this is not a boolean")`

Retourneert false.
