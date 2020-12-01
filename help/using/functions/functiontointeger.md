---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: Meer informatie over de functie toInteger
translation-type: tm+mt
source-git-commit: e2f7c39e61118c42272f730cf5f688ee34d6a9c2
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 7%

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
