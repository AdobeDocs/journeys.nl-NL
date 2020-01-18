---
title: toDecimal
description: Meer informatie over de functie toDecimal
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


# toDecimal {#toDecimal}

Zet een argumentwaarde in een decimale waarde om, afhankelijk van het type.

## Categorie

Conversie

## Functiesyntaxis

`toDecimal(<parameter>)`

## Parameters

| Parameter | Beschrijving |
|--- |--- |
|  string | converteert de tekenreekswaarde als een decimaal |
| dateTime | zet de datum om als aantal milliseconden (epoch milliseconds) |
| boolean | Zet de booleaanse waarde om als 1 indien true, 0 indien false |
| integer | wordt omgezet in decimaal (voorbeeld.: 1 wordt 1,0) |

## Handtekeningen en geretourneerde typen

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Retourneer een decimaal.

## Voorbeelden

`toDecimal("4.0")`

Retourneert 4.0.
