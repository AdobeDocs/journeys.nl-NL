---
title: toInteger
description: Meer informatie over de functie toInteger
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

---


# toInteger {#toInteger}

Zet een argumentwaarde in een geheel getal om.

## Categorie

Conversie

## Functiesyntaxis

`toInteger(<parameter>)`

## Parameters

| Parameter | Beschrijving |
|--- |--- |
|  string | converteert de tekenreekswaarde als een geheel getal |
| dateTime | zet de datum om als aantal milliseconden (epoch milliseconds) |
| decimaal | converteert naar geheel getal door het decimale gedeelte te verwijderen (voorbeeld: 1,5 wordt 1) |
| boolean | Zet de booleaanse waarde om als 1 indien true, 0 indien false |

## Handtekeningen en type geretourneerd

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Retourneer een geheel getal.

## Voorbeelden

`toInteger(4)`

Retourneert 4.
