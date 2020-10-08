---
title: Voorwaardeactiviteit
description: Meer informatie over voorwaardenactiviteiten
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 8%

---


# Voorwaardeactiviteit{#section_e2n_pft_dgb}

Er zijn vier soorten voorwaarden beschikbaar:

* [Gegevensbronvoorwaarde](#data_source_condition)
* [Tijdvoorwaarde](#time_condition)
* [Percentage splitsing](#percentage_split)
* [Datumvoorwaarde](#date_condition)

![](../assets/journey49.png)

## Informatie over de Condition-activiteit {#about_condition}

Wanneer u verschillende voorwaarden in een reis gebruikt, kunt u labels voor elk van deze voorwaarden definiëren om ze gemakkelijker te kunnen identificeren.

Klik **[!UICONTROL Add a path]** als u meerdere voorwaarden wilt definiëren. Voor elke voorwaarde wordt een nieuw pad toegevoegd in het canvas na de activiteit.

![](../assets/journey47.png)

Merk op dat het ontwerp van de reizen functionele gevolgen heeft. Wanneer meerdere paden na een voorwaarde worden gedefinieerd, wordt alleen het eerste in aanmerking komende pad uitgevoerd. Dit betekent dat u de prioritering van paden kunt wijzigen door deze boven of onder elkaar te plaatsen.

Laten we bijvoorbeeld het voorbeeld nemen van de voorwaarde &#39;De persoon is een VIP&#39; van een eerste pad en de voorwaarde &#39;De persoon is een man&#39; van een tweede pad. Als een persoon die aan beide voorwaarden voldoet (een man die een VIP is) deze stap doorstaat, wordt het eerste pad gekozen, zelfs als hij ook in aanmerking komt voor het tweede pad, omdat het eerste pad &quot;boven&quot; is. Verplaats uw activiteiten in een andere verticale volgorde om deze prioriteit te wijzigen.

![](../assets/journey48.png)

U kunt een ander pad maken voor soorten publiek die niet in aanmerking komen voor de gedefinieerde voorwaarden door dit te controleren **[!UICONTROL Show path for other cases than the one(s) above]**. Deze optie is niet beschikbaar in gesplitste omstandigheden. Zie [Percentage splitsing](#percentage_split).

In de eenvoudige modus kunt u eenvoudige query&#39;s uitvoeren op basis van een combinatie van velden. Alle beschikbare velden worden links op het scherm weergegeven. Sleep velden naar de hoofdzone. Als u de verschillende elementen wilt combineren, koppelt u ze aan elkaar om verschillende groepen en/of groepsniveaus te maken. Vervolgens kiest u een logische operator om elementen op hetzelfde niveau te combineren:

* EN: een doorsnede van twee criteria. Alleen de elementen die aan alle criteria voldoen, worden in aanmerking genomen.
* OF: een unie van twee criteria . Elementen die ten minste aan een van de twee criteria voldoen, worden in aanmerking genomen.

![](../assets/journey64.png)

Als u de [Adobe Experience Platform Segmentation Service](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html) gebruikt om uw segmenten te creëren, kunt u hen in uw reisvoorwaarden hefboomwerking. Zie Segmenten [gebruiken in voorwaarden](../segment/using-a-segment.md).


>[!NOTE]
>
>U kunt geen vragen op tijdreeksen (bijvoorbeeld een lijst van aankopen, voorbij klikken op berichten) met de eenvoudige redacteur uitvoeren. Hiervoor moet u de geavanceerde editor gebruiken. Zie [](../expression/expressionadvanced.md).


Wanneer er een fout in een actie of een voorwaarde optreedt, eindigt de journey van een individu. De enige manier om door te gaan is het selectievakje **[!UICONTROL Add an alternative path in case of a timeout or an error]** in te schakelen. Zie [](../building-journeys/using-the-journey-designer.md#paths).

## Gegevensbronvoorwaarde {#data_source_condition}

Hierdoor kunt u een voorwaarde definiëren op basis van velden uit de gegevensbronnen of de gebeurtenissen die eerder in de reis zijn geplaatst. Zie voor meer informatie over het gebruik van de expressieeditor [](../expression/expressionadvanced.md). Met de geavanceerde expressieeditor kunt u geavanceerdere voorwaarden instellen voor het manipuleren van verzamelingen of het gebruik van gegevensbronnen waarvoor parameters moeten worden doorgegeven. Zie [](../datasource/external-data-sources.md).

![](../assets/journey50.png)

## Tijdvoorwaarde{#time_condition}

Hierdoor kunt u verschillende handelingen uitvoeren op basis van het uur van de dag en/of de dag van de week. U kunt bijvoorbeeld besluiten SMS-berichten overdag en &#39;s nachts tijdens weekdagen te verzenden.

>[!NOTE]
>
>De tijdzone is niet langer specifiek voor een bepaalde aandoening en wordt nu op het niveau van de reis gedefinieerd in de reiseigenschappen. Zie [](../building-journeys/timezone-management.md).

![](../assets/journey51.png)

## Percentage splitsing {#percentage_split}

Met deze optie kunt u het publiek willekeurig opsplitsen om een andere actie voor elke groep te definiëren. Definieer het aantal splitsingen en de verdeling voor elk pad. De gesplitste berekening is statistisch, aangezien het systeem niet kan voorspellen hoeveel mensen in deze activiteit van de reis zullen stromen. Als gevolg hiervan heeft de splitsing een zeer lage foutmarge. Deze functie is gebaseerd op een willekeurig Java-mechanisme (zie deze [pagina](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)).

>[!NOTE]
>
>Er is geen knop om een pad toe te voegen in de splitsingsvoorwaarde voor percentages. Het aantal paden is afhankelijk van het aantal splitsingen. In gesplitste omstandigheden kunt u geen pad toevoegen voor andere gevallen omdat dit niet kan gebeuren. Mensen gaan altijd in een van de gesplitste paden.


![](../assets/journey52.png)

## Datumvoorwaarde {#date_condition}

Hierdoor kunt u een andere stroom definiëren op basis van de datum. Bijvoorbeeld, als de persoon de stap tijdens de &quot;verkoop&quot;periode ingaat, zult u hem een specifiek bericht verzenden. De rest van het jaar zal je nog een bericht sturen.

>[!NOTE]
>
>De tijdzone is niet langer specifiek voor een bepaalde aandoening en wordt nu op het niveau van de reis gedefinieerd in de reiseigenschappen. Zie [](../building-journeys/timezone-management.md).

![](../assets/journey53.png)
