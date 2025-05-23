---
product: adobe campaign
title: Informatie over het maken van reizen
description: Als zakelijke gebruiker leert u hoe u evenement-, orkestratie- en actieactiviteiten kunt combineren om een journey te maken.
feature: Journeys
role: User
level: Intermediate
exl-id: 540b5142-9323-4cc1-9b5a-3fa20a5945bf
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 8%

---

# Journey maken {#concept_gq5_sqt_52b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Deze stap wordt uitgevoerd door de **bedrijfsgebruiker**. Hier maak je je reizen. Combineer de verschillende gebeurtenis-, organisatie- en actieactiviteiten om uw meerstapsscenario&#39;s voor meerdere kanalen te maken.

Met de interface voor reizen kunt u activiteiten van het palet gemakkelijk naar het canvas slepen. U kunt ook dubbelklikken op een activiteit om deze in het canvas toe te voegen bij de volgende beschikbare stap. Elke activiteit heeft een specifieke rol en plaats in het proces. De activiteiten worden gesequenceerd. Wanneer een activiteit wordt gebeëindigd, gaat de stroom verder en verwerkt de volgende activiteit, etc.

Per reis is slechts één naamruimte toegestaan. Wanneer u de eerste gebeurtenis neerzet, worden gebeurtenissen met verschillende naamruimten grijs weergegeven. Als de eerste gebeurtenis geen naamruimte heeft, worden alle gebeurtenissen met een naamruimte grijs weergegeven. Zie [ deze pagina ](../event/selecting-the-namespace.md). Bovendien worden Adobe Experience Platform-veldgroepen grijs weergegeven als de rit gebeurtenissen zonder naamruimte bevat. En tot slot, als u verscheidene gebeurtenissen in de zelfde reis gebruikt, moeten zij zelfde namespace gebruiken.

Bij het starten van een nieuwe rit worden elementen die niet op het canvas kunnen worden neergezet als de eerste stap, verborgen. Dit heeft betrekking op alle handelingen, de activiteit van de aandoening, de wachttijd en de reactie.

## Snel starten {#creating_journey}

Hier volgen de belangrijkste stappen voor het maken en publiceren van een reis.

1. Klik in het bovenste menu op het tabblad **[!UICONTROL Home]**.

   De lijst met reizen wordt weergegeven. Verwijs naar [ deze pagina ](../building-journeys/using-the-journey-designer.md) voor meer informatie over de interface.

   ![](../assets/journey30.png)

1. Klik op **[!UICONTROL Create]** om een nieuwe rit te maken.

   ![](../assets/journey31.png)

1. Bewerk de eigenschappen van de journey in het configuratievenster dat aan de rechterkant wordt weergegeven. Zie [deze pagina](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Begin door een gebeurtenisactiviteit van het palet naar het canvas te slepen. U kunt ook dubbelklikken op een activiteit om deze aan het canvas toe te voegen.

   ![](../assets/journey33.png)

1. Sleep en zet uw andere activiteiten neer en vorm hen. Verwijs naar de pagina&#39;s [ activiteiten van de Gebeurtenis ](../building-journeys/event-activities.md), [ Ongeveer orchestratieactiviteiten ](../building-journeys/about-orchestration-activities.md) en [ Ongeveer actieactiviteiten ](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Uw reis wordt automatisch bewaard. Test uw reis en publiceer deze. Zie [ het testen van de reis ](../building-journeys/testing-the-journey.md) en [ het Publiceren van de reis ](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Een reis beëindigen {#ending_a_journey}

Een reis kan om twee redenen eindigen:

* De persoon komt bij de laatste activiteit van een weg aan. Deze laatste activiteit kan een eindactiviteit of een andere activiteit zijn. Er bestaat geen verplichting om een pad met een eindactiviteit te beëindigen. Zie [deze pagina](../building-journeys/end-activity.md).
* De persoon komt bij een voorwaardenactiviteit (of een wachttijdactiviteit met een voorwaarde) aan en past geen van de voorwaarden aan.

De persoon kan dan opnieuw de reis betreden als herbinnenkomst is toegestaan. Zie [deze pagina](../building-journeys/changing-properties.md).

Een reis kan om de volgende redenen worden gesloten:

* De reis wordt manueel gesloten via de **[!UICONTROL Close to new entrances]** knoop.
* De einddatum van de reis is bereikt.

Wanneer een reis wordt gesloten (om een van de bovenstaande redenen), heeft deze de status **[!UICONTROL Closed]** . De reis zal het niet langer mogelijk maken dat nieuwe individuen de reis betreden. Personen die al op reis zijn, zullen de reis normaal afmaken. Na standaard globale onderbreking van 30 dagen, zal de reis aan de **Voltooide** status schakelen. Zie deze [ sectie ](../building-journeys/changing-properties.md#entrance).

Als u de voortgang van alle mensen op de reis moet stoppen, kunt u deze stoppen. Als de reis wordt stopgezet, wordt een time-out voor alle personen op de reis vastgesteld.

Leren hoe te om een reis manueel te sluiten of tegen te houden, verwijs naar deze [ sectie ](../building-journeys/terminating-a-journey.md).
