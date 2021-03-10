---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: Meer informatie over de functie nowWithDelta
feature: Reizen
role: Gegevensengineer
level: Ervaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 5%

---


# nowWithDelta {#nowWithDelta}

Retourneert de huidige datumtijd inclusief een verschuiving. Als een tijdzone-id wordt opgegeven, wordt de verschuiving van de tijdzone toegepast. Raadpleeg [deze pagina](../expression/data-types.md) voor meer informatie over gegevenstypen.

## Categorie

Datum

## Functiesyntaxis

`nowWithDelta(<parameters>)`

## Parameters

| Parameter | Beschrijving |
|--- |--- |
| delta | positieve of negatieve gehele waarde |
| datumonderdeel | jaar, maanden, dagen, uren, minuten of seconden als een tekenreeks |
| tijdzone-id | tekenreeksrepresentatie van de tijdzonewaarde. Zie [Gegevenstypen](../expression/data-types.md) voor meer informatie. Tijdzone-id moet een tekenreeksconstante zijn. Het kan geen veldverwijzing of expressie zijn. |

## Handtekeningen en type geretourneerd

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Retourneert een dateTime.

## Voorbeelden

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Retourneert precies 2 uur geleden een dateTime.
