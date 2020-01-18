---
title: Over het eenvoudige gebruik
description: Meer informatie over de reis, eenvoudig gebruik
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
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab

---


# Over het eenvoudige gebruik{#concept_grh_vby_w2b}

## Doel {#purpose}

Laten we het voorbeeld nemen van een hotelmerk genaamd Marlton. In hun hotels hebben ze baken-apparaten in de buurt van alle strategische gebieden geplaatst: lobby, vloeren, restaurant, gym, pool, enz.

In dit gebruiksgeval, zullen wij zien hoe te om een gepersonaliseerd bericht in real time naar een persoon te verzenden die naast een baken loopt die dichtbij de spanwijdte wordt geplaatst.

We willen alleen een bericht sturen als de persoon een vrouw is. Het bericht moet binnen seconden worden ontvangen.

![](../assets/journeyuc1_16.png)

## Voorwaarden {#prerequisites}

Voor ons gebruiksgeval hebben we één e-mailsjabloon voor berichten over transacties ontworpen in Adobe Campagne Standard. We gebruiken een berichtensjabloon voor een gebeurtenistransactie. Zie deze [pagina](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard is geconfigureerd om e-mailberichten te verzenden.

De gebeurtenissen worden verzonden van de mobiele telefoon van de klanten wanneer zij dichtbij een baken worden ontdekt. U moet een mobiele toepassing ontwerpen om gebeurtenissen van de mobiele telefoon van de klant naar de mobiele SDK te verzenden.