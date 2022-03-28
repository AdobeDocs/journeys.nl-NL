---
product: adobe campaign
title: Gebeurtenisactiviteiten
description: Learn about events activities
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: 5b09ed456b6a9645dbb7897481317d3904e29d31
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# Gebeurtenisactiviteiten {#concept_rws_1rt_52b}

De gebeurtenissen die door de technische gebruiker worden gevormd (zie [deze pagina](../event/about-events.md)) worden allemaal weergegeven in de eerste categorie van het palet, links op het scherm.

![](../assets/journey43.png)

Always start your journey by drag and dropping an event activity. U kunt er ook op dubbelklikken.

![](../assets/journey44.png)

Wanneer u op de gebeurtenisactiviteit in het canvas klikt, wordt de ruit van de activiteitenconfiguratie getoond. Wanneer u dezelfde gebeurtenis meerdere keren gebruikt, wordt standaard een verhoogd getal toegevoegd aan de naam van de gebeurtenis op het canvas. Daarnaast kunt u de opdracht **[!UICONTROL Label]** veld om een achtervoegsel toe te voegen aan de naam van de gebeurtenis die onder uw activiteit op het canvas wordt weergegeven. Dit is handig als u gebeurtenissen op het canvas wilt identificeren, vooral als u dezelfde gebeurtenis meerdere keren gebruikt. It will also make debugging easier in case of errors and it will make reports easier to read.

![](../assets/journey33.png)

## Luisteren naar gebeurtenissen tijdens een bepaald tijdstip

Een gebeurtenisactiviteit die in de reis wordt geplaatst luistert voor onbepaalde tijd naar gebeurtenissen. Als u alleen tijdens een bepaalde tijd naar een gebeurtenis wilt luisteren, moet u een time-out voor de gebeurtenis configureren.

De reis zal dan aan de gebeurtenis tijdens de tijd luisteren die in de timeout wordt gespecificeerd. If an event is received during that period, the person will flow in the event path. Als niet, zal de klant of in een onderbrekingspad stromen, of hun reis beëindigen.

Voer de volgende stappen uit om een time-out voor een gebeurtenis te configureren:

1. De **[!UICONTROL Enable the event timeout]** van de eigenschappen van de gebeurtenis.

1. Geef op hoeveel tijd de reis moet wachten op de gebeurtenis.

1. If you want to send the individuals into a timeout path when no event is received within the specified timeout, enable the **[!UICONTROL Set the timeout path]** option. If this option is not enabled, the journey will end for the individual once the timeout is reached.

   ![](../assets/event-timeout.png)

In dit voorbeeld, verzendt de reis een eerste welkome duw naar een klant. Het verzendt dan een duw van de maaltijdkorting slechts als de klant het restaurant binnen de volgende dag ingaat. Daarom hebben we de restaurant-gebeurtenis geconfigureerd met een time-out van 1 dag:

* If the restaurant event is received less than 1 day after the welcome push, the meal discount push activity is sent.
* Als er de volgende dag geen restaurantgebeurtenis wordt ontvangen, loopt de persoon door het time-outpad.

Merk op dat als u een onderbreking op veelvoudige gebeurtenissen wilt vormen die na a worden geplaatst **[!UICONTROL Wait]** activiteit, moet u de onderbreking op één van deze gebeurtenissen slechts vormen.

De time-out wordt toegepast op alle gebeurtenissen na de gebeurtenis **[!UICONTROL Wait]** activiteit. Als er geen gebeurtenis is ontvangen vóór de opgegeven time-out, gaan de personen naar één enkel time-outpad of beëindigen ze hun reis.

![](../assets/event-timeout-group.png)
