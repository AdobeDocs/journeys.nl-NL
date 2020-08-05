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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---



# Tijdzonebeheer {#timezone_management}

U kunt een tijdzone in de [eigenschappen](../building-journeys/changing-properties.md) van uw reis bepalen.

Als u eigenschappen wilt openen, klikt u op het potloodpictogram rechtsboven in het scherm.

Deze tijdzone wordt gebruikt voor elke activiteit van de reis die een tijdselement bevat, zoals:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

U kunt een tijdzone selecteren of de tijdzone gebruiken die is gedefinieerd in het gebruikersprofiel.

## Een vaste tijdzone definiëren {#fixed-timezone}

De tijdzone kan ook worden vastgesteld. Wis de vooraf gedefinieerde tijdzone en kies een tijdzone in de vervolgkeuzelijst. Als je een vaste tijdzone gebruikt, zal dat hetzelfde zijn voor iedereen die de reis binnenkomt.

U doet dit door in **[!UICONTROL Properties]** een tijdzone te selecteren.

![](../assets/journey73.png)

## Profielen gebruiken om de tijdzone voor het transport te definiëren {#timezone-from-profiles}

Als de entry-gebeurtenis van de reis een naamruimte heeft, wat betekent dat de reis de Real-time dienst van het Profiel van de Klant van de Adobe Experience Platform kan bereiken, is de tijdzone vooraf gedefinieerd met die gespecificeerd in het profiel van de individuele die in de reis stroomt.

Als een tijdzone wordt gedefinieerd in het Adobe Experience Platform-profiel, kan deze tijdens de reis worden opgehaald.

Als het profiel van het individu geen tijdzone bevat, wordt de opgehaalde tijdzone gedefinieerd in het tijdzoneveld.

Om dit te doen, in **[!UICONTROL Properties]**, controleer **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey72.png)

## Tijdzones gebruiken in expressies {#timezone-in-expressions}

De begin- en einddatum van een reis kunnen niet worden gekoppeld aan een specifieke tijdzone. Ze worden automatisch gekoppeld aan de tijdzone van de instantie.
