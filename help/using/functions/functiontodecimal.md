---
product: adobe campaign
title: toDecimal
description: Meer informatie over de functie toDecimal
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 9%

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
