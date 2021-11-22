---
product: adobe campaign
title: Tijdzonebeheer
description: Meer informatie over tijdzonebeheer
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 2%

---

# Tijdzonebeheer {#timezone_management}

U kunt een tijdzone definiëren in het dialoogvenster [eigenschappen](../building-journeys/changing-properties.md) van je reis.

Als u eigenschappen wilt openen, klikt u op het potloodpictogram rechtsboven in het scherm.

Deze tijdzone wordt gebruikt voor elke activiteit van de reis die een tijdselement bevat, zoals:

* [Tijdvoorwaarde](../building-journeys/condition-activity.md#time_condition)
* [Datumvoorwaarde](../building-journeys/condition-activity.md#date_condition)
* [Aangepast wachten](../building-journeys/wait-activity.md#custom)
* [Wachttijd voor vaste datum](../building-journeys/wait-activity.md#fixed_date)

U kunt een tijdzone selecteren of de tijdzone gebruiken die is gedefinieerd in het gebruikersprofiel.

>[!NOTE]
>
>De tijdzone van het profiel werkt met **timeZone** in het **Voorkeursdetails** veldgroep.

## Een vaste tijdzone definiëren {#fixed-timezone}

De tijdzone kan ook worden vastgesteld. Wis de vooraf gedefinieerde tijdzone en kies een tijdzone in de vervolgkeuzelijst. Als je een vaste tijdzone gebruikt, zal dat hetzelfde zijn voor iedereen die de reis binnenkomt.

Daartoe, in **[!UICONTROL Properties]** selecteert u een tijdzone.

![](../assets/journey72.png)

## Profielen gebruiken om de tijdzone voor het transport te definiëren {#timezone-from-profiles}

Als de entry-gebeurtenis van de reis een naamruimte heeft, wat betekent dat de reis de Real-time dienst van het Profiel van de Klant van de Adobe Experience Platform kan bereiken, is de tijdzone vooraf gedefinieerd met die gespecificeerd in het profiel van de individuele die in de reis stroomt.

Als een tijdzone wordt gedefinieerd in het Adobe Experience Platform-profiel, kan deze tijdens de reis worden opgehaald.

Als het profiel van het individu geen tijdzone bevat, wordt de opgehaalde tijdzone gedefinieerd in het tijdzoneveld.

Daartoe, in **[!UICONTROL Properties]**, controle **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey73.png)

## Tijdzones gebruiken in expressies {#timezone-in-expressions}

De begin- en einddatum van een reis kunnen niet worden gekoppeld aan een specifieke tijdzone. Ze worden automatisch gekoppeld aan de tijdzone van de instantie.
