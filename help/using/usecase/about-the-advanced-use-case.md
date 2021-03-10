---
product: adobe campaign
solution: Journey Orchestration
title: Informatie over geavanceerde gebruiksscenario's
description: 'Meer informatie over de reis: geavanceerde gebruiksscenario'
feature: Reizen
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 4%

---


# Informatie over geavanceerde gebruiksscenario&#39;s{#concept_vzy_ncy_w2b}

## Doel {#purpose}

Laten we het voorbeeld nemen van een hotelmerk genaamd Marlton. In hun hotels hebben ze baken-apparaten in de buurt van alle strategische gebieden geplaatst: lobby, vloeren, restaurant, gym, pool, enz.

>[!NOTE]
>
>In dit geval gebruiken we Adobe Campaign Standard om berichten te verzenden.

In dit gebruiksgeval, zullen wij zien hoe te om gepersonaliseerde berichten in real time naar klanten te verzenden wanneer zij dichtbij een specifiek baken lopen.

Allereerst willen we een bericht sturen zodra iemand een Marlton-hotel binnenkomt. We willen alleen een bericht sturen als de persoon geen communicatie van ons heeft ontvangen binnen de afgelopen 24 uur.

Vervolgens controleren we twee voorwaarden:

* Als deze persoon geen loyaliteitslid is, sturen we hem een e-mail om zich aan te sluiten bij het aanbod voor loyaliteitslidmaatschap.
* Als deze persoon al een loyaliteitslid is, controleren we of hij een reservering voor een kamer heeft:
   * Als hij dat niet doet, sturen we hem een pushmelding met kamertarieven.
   * Als hij dat doet, sturen we hem een welkome pushmelding. Als hij binnen de komende 6 uur het restaurant binnenkomt, sturen we hem een pushmelding met een korting op een maaltijd.

![](../assets/journeyuc2_29.png)

Voor dit gebruiksgeval, zullen wij twee gebeurtenissen moeten tot stand brengen (zie [deze pagina](../usecase/configuring-the-events.md)):

* De lobby-gebeurtenis die naar het systeem wordt geduwd wanneer een klant het hotel binnenkomt.
* De bakengebeurtenis van het restaurant die zal worden geduwd wanneer een klant het restaurant ingaat.

We moeten een verbinding met twee gegevensbronnen configureren (zie [deze pagina](../usecase/configuring-the-data-sources.md)):

* De ingebouwde gegevensbron van Adobe Experience Platform, om de informatie voor onze twee voorwaarden (loyaliteitslidmaatschap en laatste contactdatum) evenals de informatie van de berichtverpersoonlijking terug te winnen.
* Het hotelreserveringssysteem om de informatie over de reserveringsstatus op te halen.

## Voorwaarden {#prerequisites}

Voor ons gebruik hebben we drie Adobe Campaign Standard-sjablonen voor transactieberichten ontworpen. We gebruiken transactiesjablonen voor gebeurtenissen. Zie deze [pagina](https://docs.adobe.com/content/help/nl-NL/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard is geconfigureerd voor het verzenden van e-mails en pushberichten.

De Experience Cloud-id wordt gebruikt als sleutel om de klant in het reserveringssysteem voor hotels te identificeren.

De gebeurtenissen worden verzonden van de mobiele telefoon van de klanten wanneer zij dichtbij een baken ontdekten. U moet een mobiele toepassing ontwerpen om gebeurtenissen van de mobiele telefoon van de klant naar de mobiele SDK te verzenden.

Het veld Loyalty-lid is een aangepast veld en is toegevoegd in XDM voor onze specifieke organisatie-id.
