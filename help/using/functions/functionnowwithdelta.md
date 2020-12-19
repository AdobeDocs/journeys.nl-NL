---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: Meer informatie over de functie nowWithDelta
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 4%

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
