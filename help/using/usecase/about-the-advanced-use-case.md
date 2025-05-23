---
product: adobe campaign
title: Geavanceerde gebruiksscenario's
description: 'Meer informatie over de reis: geavanceerde gebruiksscenario'
feature: Journeys
role: User
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 2%

---

# Geavanceerde gebruiksscenario&#39;s{#concept_vzy_ncy_w2b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


## Doel {#purpose}

Laten we het voorbeeld nemen van een hotelmerk genaamd Marlton. In hun hotels hebben ze baken-apparaten in de buurt van alle strategische gebieden geplaatst: lobby, vloeren, restaurant, gym, pool, enz.

>[!NOTE]
>
>In dit geval gebruiken we Adobe Campaign Standard om berichten te verzenden.

In dit gebruiksgeval, zullen wij zien hoe te om gepersonaliseerde berichten in real time naar klanten te verzenden wanneer zij dichtbij een specifiek baken lopen.

Allereerst willen we een bericht sturen zodra iemand een Marlton-hotel binnenkomt. We willen alleen een bericht sturen als de persoon geen communicatie van ons heeft ontvangen binnen de afgelopen 24 uur.

Vervolgens controleren we twee voorwaarden:

* Als deze persoon geen loyaliteitslid is, sturen wij hen een e-mail om zich bij het loyaliteitslidmaatschapsaanbod aan te sluiten.
* Als deze persoon al een loyaliteitslid is, controleren we of hij een reservering voor een kamer heeft:
   * Als hij dat niet doet, sturen we ze een pushmelding met kamertarieven.
   * Als hij dat doet, sturen we ze een welkome pushmelding. Als hij binnen de komende 6 uur het restaurant binnenkomt, sturen we ze een pushmelding met een korting op een maaltijd.

![](../assets/journeyuc2_29.png)

Voor dit gebruiksgeval, zullen wij twee gebeurtenissen moeten tot stand brengen (zie [ deze pagina ](../usecase/configuring-the-events.md)):

* De lobby-gebeurtenis die naar het systeem wordt geduwd wanneer een klant het hotel binnenkomt.
* De bakengebeurtenis van het restaurant die zal worden geduwd wanneer een klant het restaurant ingaat.

Wij zullen een verbinding aan twee gegevensbronnen (zie [ moeten vormen deze pagina ](../usecase/configuring-the-data-sources.md)):

* De ingebouwde gegevensbron van Adobe Experience Platform, om de informatie voor onze twee voorwaarden (loyaliteitslidmaatschap en laatste contactdatum) evenals de informatie van de berichtverpersoonlijking terug te winnen.
* Het hotelreserveringssysteem om de informatie over de reserveringsstatus op te halen.

## Voorwaarden {#prerequisites}

Voor ons gebruik hebben we drie Adobe Campaign Standard-sjablonen voor transactieberichten ontworpen. We gebruiken transactiesjablonen voor gebeurtenissen. Verwijs naar deze [ pagina ](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=nl).

Adobe Campaign Standard is geconfigureerd voor het verzenden van e-mails en pushberichten.

De Experience Cloud-id wordt gebruikt als sleutel voor de identificatie van de klant in het reserveringssysteem voor hotels.

De gebeurtenissen worden verzonden van de mobiele telefoon van de klanten wanneer zij dichtbij een baken ontdekten. U moet een mobiele toepassing ontwerpen om gebeurtenissen van de mobiele telefoon van de klant naar de mobiele SDK te verzenden.

Het veld Loyalty-lid is een aangepast veld en is toegevoegd in XDM voor onze specifieke organisatie-id.
