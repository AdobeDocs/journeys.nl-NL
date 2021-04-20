---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: Meer informatie over de functie toDecimal
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 8%

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
| string | converteert de tekenreekswaarde als een decimaal |
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
