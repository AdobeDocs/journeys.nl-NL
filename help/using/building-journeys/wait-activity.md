---
title: Wacht op activiteit
description: Meer informatie over wachtactiviteiten
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
source-git-commit: 3f8f7eb34a11f0ff87ed3c55e7294b5bdbfb9383

---


# Wacht op activiteit{#section_rlm_nft_dgb}

Als u wilt wachten alvorens de volgende activiteit in de weg uit te voeren, kunt u een **[!UICONTROL Wait]** activiteit gebruiken. Hiermee kunt u bepalen wanneer de volgende activiteit wordt uitgevoerd. Er zijn vier opties beschikbaar:

* [Duur](#duration)
* [Vaste datum](#fixed_date)
* [Aangepast](#custom)
* [Optimalisatie van verzendtijd voor e-mail](#email_send_time_optimization)

## Informatie over de activiteit Wachten{#about_wait}

Hier is hoe de wacht voorrang krijgt wanneer u verscheidene wacht parallel gebruikt. Als zij de zelfde tijdconfiguratie en een verschillende maar overlappende voorwaarde hebben, hierboven gepositioneerde wachttijd zal aan voorrang gegeven zijn. Bijvoorbeeld, is de voorwaarde van eerste wacht &quot;een vrouw zijn&quot;en de voorwaarde van tweede wacht parallel is &quot;een VIP zijn&quot;. De eerste wachttijdactiviteit krijgt prioriteit

Houd er ook rekening mee dat als twee verschillende wachttijden parallel lopen, de eerste prioriteit krijgt, ongeacht de verticale positie. Bijvoorbeeld, als een 1 uur wacht boven is en een 30 minuut wacht onder is, na 30 minuten, zal het 30 minieme ogenblik worden verwerkt.

U kunt een voorwaarde definiëren als u de wachttijd wilt beperken tot een bepaalde populatie.

>[!NOTE]
>
>De maximale wachttijd is 30 dagen.
>
>Op testwijze, staat de **** Wacht tijd in testparameter u toe om de tijd te bepalen dat elke wachttijdactiviteit zal duren. De standaardtijd is 10 seconden. Zo krijgt u de testresultaten snel. Zie [](../building-journeys/testing-the-journey.md)

## Wachttijd duur{#duration}

Selecteer de duur van de wachttijd voordat de volgende activiteit wordt uitgevoerd.

![](../assets/journey55.png)

## Wachttijd voor vaste datum{#fixed_date}

Selecteer de datum voor de uitvoering van de volgende activiteit.

![](../assets/journey56.png)

## Aangepast wachten{#custom}

Met deze optie kunt u een aangepaste datum definiëren, bijvoorbeeld 12 juli 2020 om 17.00 uur, met een geavanceerde expressie die is gebaseerd op een veld dat afkomstig is van een gebeurtenis of gegevensbron. U kunt hiermee geen aangepaste duur definiëren, bijvoorbeeld 7 dagen. De expressie in de expressie-editor moet een dateTimeOnly-indeling hebben. Zie [](../expression/expressionadvanced.md). Zie voor meer informatie over de indeling dateTimeOnly [](../expression/data-types.md).

>[!NOTE]
>
>U kunt een dateTimeOnly-expressie gebruiken of een functie gebruiken om om te zetten in een dateTimeOnly. Bijvoorbeeld: toDateTimeOnly(@{Event.biedOpened.activity.endTime}), waarbij het veld in de gebeurtenis de vorm 2016-08-12T09:46:06 heeft.
>
>De **tijdzone** wordt verwacht in de eigenschappen van uw reis. Dientengevolge, is het vandaag niet mogelijk van de interface om bij volledig ISO-8601 timestamp mixing time en tijdzone verschuiving zoals 2016-08-12T09:46:06.982-05 direct te richten. Zie [](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

## Optimalisatie van verzendtijd voor e-mail{#email_send_time_optimization}

>[!CAUTION]
>
>De functie voor het optimaliseren van de verzendtijd van e-mail is alleen beschikbaar voor klanten die de functie Adobe Campagne Standard Data Service gebruiken.

Bij dit type wachttijd wordt een score gebruikt die in het Platform is berekend. De score berekent de neiging om in de toekomst op e-mail te klikken of te openen op basis van gedrag uit het verleden. Merk op dat het algoritme dat de score berekent een bepaalde hoeveelheid gegevens vereist om te werken. Als er onvoldoende gegevens zijn, is de standaardwachttijd dus van toepassing. Tijdens de publicatie wordt u op de hoogte gesteld dat de standaardtijd van toepassing is.

>[!NOTE]
>
>De eerste gebeurtenis van uw reis moet een namespace hebben.
>
>Deze mogelijkheid is alleen beschikbaar na een **[!UICONTROL Email]** activiteit. U hebt Adobe Campaign Standard nodig.

1. Definieer in het **[!UICONTROL Amount of time]** veld het aantal uren dat u wilt overwegen om het verzenden van e-mail te optimaliseren.
1. Kies in het **[!UICONTROL Optimization type]** veld of er meer moet worden geklikt of dat er meer moet worden geopend.
1. Definieer in het veld **Standaardtijd** de standaardtijd die u wilt wachten als de voorspellende score voor de verzendtijd niet beschikbaar is.

   >[!NOTE]
   >
   >De score voor de verzendtijd kan niet beschikbaar zijn omdat er onvoldoende gegevens zijn om de berekening uit te voeren. In dit geval wordt u tijdens de publicatie ervan op de hoogte gesteld dat de standaardtijd van toepassing is.

![](../assets/journey57bis.png)
