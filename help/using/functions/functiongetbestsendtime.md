---
title: getBestSendTime
description: Meer informatie over de functie getBestSendTime
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# getBestSendTime {#getBestSendTime}

Biedt een voorspelbare tijd voor het leveren van een e-mail aan een individu.

Deze functie gebruikt een score die in het Platform wordt berekend. De score berekent de neiging om in de toekomst op e-mail te klikken of te openen op basis van gedrag uit het verleden. Merk op dat het algoritme dat de score berekent een bepaalde hoeveelheid gegevens vereist om te werken. Als er onvoldoende gegevens zijn, is de standaardtijd dus van toepassing. Zie voor meer informatie [](../building-journeys/wait-activity.md).

Voor het gebruik van deze functie is een [naamruimte](../event/selecting-the-namespace.md) nodig.

>[!NOTE]
>
>De beste verzendtijdscore kan niet beschikbaar zijn als er onvoldoende gegevens zijn om de berekening uit te voeren. In dit geval wordt u tijdens de publicatie ervan op de hoogte gesteld dat de standaardtijd van toepassing is.

## Categorie

Adobe Experience Platform

## Functiesyntaxis

`getBestSendTime(<parameters>)`

## Parameters

| Parameter | Beschrijving | Type |
|--- |--- |--- |
| tijdsduur | Aantal te overwegen uren van de huidige tijd (maximum: 168) om e-mailverzending te optimaliseren | `<integer>` |
| optimalisatietype | &quot;open&quot; of &quot;click&quot; | `<string>` |
| standaardtijd in uren om te wachten | Als de voorspellende scores voor de verzendtijd niet beschikbaar zijn | `<integer>` |

## Handtekening en type geretourneerd

`getBestSendTime(<integer>,<string>,<integer>)`

Retourneert een dateTime.

## Voorbeeld

getBestSendTime(12,&quot;open&quot;,8)

Toelichting:

De functie zal de beste tijd terugkeren om een bericht in de volgende 12 uren te verzenden, om de waarschijnlijkheid te optimaliseren voor het individu in de reisinstantie om het te openen. Als er onvoldoende gegevens zijn om de berekening uit te voeren, is de geretourneerde tijd 8 uur na de huidige tijd.
