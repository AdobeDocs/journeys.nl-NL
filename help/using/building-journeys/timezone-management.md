---
title: Tijdzonebeheer
description: Meer informatie over tijdzonebeheer
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
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# Tijdzonebeheer {#timezone_management}

De definitie van de tijdzone is beschikbaar in de volgende activiteiten:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Als de entry-gebeurtenis van de reis een namespace heeft, die betekent dat de reis de dienst van het Profiel van de Klant in real time van het Platform van Gegevens kan bereiken, is de tijdzone vooraf bepaald met die gespecificeerd in het profiel van het individu dat in de reis stroomt. Als het profiel van het individu geen tijdzone bevat, wordt de tijdzone van de instantie gebruikt. U kunt contact opnemen met de beheerder om de tijdzone van de instantie te kennen.

![](../assets/journey73.png)

De tijdzone kan ook worden vastgesteld. Wis de vooraf gedefinieerde tijdzone en kies een tijdzone in de vervolgkeuzelijst. Als je een vaste tijdzone gebruikt, zal dat hetzelfde zijn voor iedereen die de reis binnenkomt.

![](../assets/journey72.png)

Tot slot kan de tijdzone dynamisch zijn voor elke persoon die de stap ingaat. In dit geval gebruikt u de expressie-editor om aan te geven waar u wilt dat het systeem deze gegevens ophaalt (dit kan een gebeurtenis of gegevensbron zijn). Zie [](../expression/expressionadvanced.md).


De begin- en einddatum van een reis kunnen niet worden gekoppeld aan een specifieke tijdzone. Ze worden automatisch gekoppeld aan de tijdzone van de instantie.
