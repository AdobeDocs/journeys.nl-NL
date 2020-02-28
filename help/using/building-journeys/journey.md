---
title: Informatie over het maken van reizen
description: Leer hoe u een reis bouwt
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
source-git-commit: d5c013ed6031e8138a8e2c099fc28af82966d3ec

---



# Een reis maken {#concept_gq5_sqt_52b}

Deze stap wordt uitgevoerd door de **bedrijfsgebruiker**. Hier maak je je reizen. Combineer de verschillende gebeurtenis-, organisatie- en actieactiviteiten om uw meerstapsscenario&#39;s voor meerdere kanalen te maken.

Met de interface voor reizen kunt u activiteiten van het palet gemakkelijk naar het canvas slepen. U kunt ook dubbelklikken op een activiteit om deze in het canvas toe te voegen bij de volgende beschikbare stap. Elke activiteit heeft een specifieke rol en plaats in het proces. De activiteiten worden gesequenceerd. Wanneer een activiteit wordt gebeëindigd, gaat de stroom verder en verwerkt de volgende activiteit, etc.

Per reis is slechts één naamruimte toegestaan. Wanneer u de eerste gebeurtenis neerzet, worden gebeurtenissen met verschillende naamruimten grijs weergegeven. Als de eerste gebeurtenis geen naamruimte heeft, worden alle gebeurtenissen met een naamruimte grijs weergegeven. Zie [](../event/selecting-the-namespace.md). Bovendien worden de de gebiedsgroepen van het Platform van de Ervaring grijs als de reis gebeurtenissen zonder namespace heeft. En tot slot, als u verscheidene gebeurtenissen in de zelfde reis gebruikt, moeten zij zelfde namespace gebruiken.

## Snel starten {#creating_journey}

Hier volgen de belangrijkste stappen voor het maken en publiceren van een reis.

1. Klik in het bovenste menu op de **[!UICONTROL Home]** tab.

   De lijst met reizen wordt weergegeven. Zie [](../building-journeys/using-the-journey-designer.md) voor meer informatie over de interface.

   ![](../assets/journey30.png)

1. Klik **[!UICONTROL Create]** om een nieuwe reis te maken.

   ![](../assets/journey31.png)

1. Bewerk de eigenschappen van de rit in het configuratievenster dat aan de rechterkant wordt weergegeven. Zie [](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Begin door een gebeurtenisactiviteit van het palet naar het canvas te slepen. U kunt ook dubbelklikken op een activiteit om deze aan het canvas toe te voegen.

   ![](../assets/journey33.png)

1. Sleep en zet uw andere activiteiten neer en vorm hen. Zie [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) en [](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Uw reis wordt automatisch bewaard. Test uw reis en publiceer deze. Zie [](../building-journeys/testing-the-journey.md) en [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Een reis beëindigen {#ending_a_journey}

Er zijn twee manieren om een reis te beëindigen:

* De persoon komt bij de laatste activiteit van een weg aan. Deze laatste activiteit kan een eindactiviteit of een andere activiteit zijn. Er bestaat geen verplichting om een pad met een eindactiviteit te beëindigen. Zie [](../building-journeys/end-activity.md).
* De persoon komt bij een voorwaardenactiviteit (of een wachttijdactiviteit met een voorwaarde) aan en past geen van de voorwaarden aan.

De persoon kan dan opnieuw de reis betreden als herbinnenkomst is toegestaan. Zie [](../building-journeys/changing-properties.md).
