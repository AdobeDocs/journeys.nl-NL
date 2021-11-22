---
product: adobe campaign
title: toInteger
description: Meer informatie over de functie toInteger
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 10%

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
| string | converteert de tekenreekswaarde als een geheel getal |
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

`toInteger("4")`

Retourneert 4.
