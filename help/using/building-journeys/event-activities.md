---
title: Gebeurtenisactiviteiten
description: Meer informatie over gebeurtenisactiviteiten
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
source-git-commit: 71b5b1ecd20056d0103ae1a8b83a31478449e844
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---


# Gebeurtenisactiviteiten {#concept_rws_1rt_52b}

De gebeurtenissen die door de technische gebruiker worden gevormd (zie [](../event/about-events.md)) worden allen getoond in de eerste categorie van het palet, op de linkerkant van het scherm.

![](../assets/journey43.png)

Begin altijd uw reis door een gebeurtenisactiviteit te slepen en neer te zetten. U kunt er ook op dubbelklikken.

![](../assets/journey44.png)

Wanneer u op de gebeurtenisactiviteit in het canvas klikt, wordt de ruit van de activiteitenconfiguratie getoond. Wanneer u dezelfde gebeurtenis meerdere keren gebruikt, wordt standaard een verhoogd getal toegevoegd aan de naam van de gebeurtenis op het canvas. Bovendien kunt u het **[!UICONTROL Label]** veld gebruiken om een achtervoegsel toe te voegen aan de naam van de gebeurtenis die onder uw activiteit op het canvas wordt weergegeven. Dit is handig als u gebeurtenissen op het canvas wilt identificeren, vooral als u dezelfde gebeurtenis meerdere keren gebruikt. Het zal ook het zuiveren in het geval van fouten gemakkelijker maken en het zal rapporten gemakkelijker te lezen maken.

![](../assets/journey33.png)

## Geavanceerd gebruik: gebeurtenissen met een wachttijd parallel{#section_vxv_h25_pgb}

**Hoe kunt u alleen tijdens een bepaalde tijd naar een gebeurtenis luisteren?**

Een gebeurtenisactiviteit die in de reis wordt geplaatst luistert voor onbepaalde tijd naar gebeurtenissen. Als u alleen gedurende een bepaalde tijd naar een gebeurtenis wilt luisteren, moet u een wachtactiviteit toevoegen parallel aan het gebeurtenispad. De reis zal dan aan de gebeurtenis tijdens de tijd luisteren die in de wachttijdactiviteit wordt gespecificeerd. Als een gebeurtenis tijdens die periode wordt ontvangen, zal de persoon in de gebeurtenisweg stromen. Als niet, zal de klant in de wachttijdweg stromen.

U hebt bijvoorbeeld een welkomstpushbericht naar een klant gestuurd en u wilt alleen een pushbericht voor maaltijdkortingen verzenden als de klant het restaurant binnen de volgende 6 uur betreedt. Hiervoor maakt u een tweede pad (parallel aan de restaurantgebeurtenis één) met een wachtactiviteit van 6 uur. Als de restaurantgebeurtenis minder dan 6 uur na de welkomstpush wordt ontvangen, wordt de pushactiviteit voor de maaltijdkorting verzonden. Als er geen restaurantgebeurtenis binnen de volgende 6 uur wordt ontvangen, loopt de persoon door het wachttijdpad.

![](../assets/journeyuc2_31.png)
