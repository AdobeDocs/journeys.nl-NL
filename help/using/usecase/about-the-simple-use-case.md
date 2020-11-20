---
product: adobe campaign
solution: Journey Orchestration
title: Informatie over eenvoudige gebruiksscenario's
description: Meer informatie over de reis, eenvoudig gebruik
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 12%

---


# Informatie over eenvoudige gebruiksscenario&#39;s{#concept_grh_vby_w2b}

## Doel {#purpose}

Laten we het voorbeeld nemen van een hotelmerk genaamd Marlton. In hun hotels hebben ze baken-apparaten in de buurt van alle strategische gebieden geplaatst: lobby, vloeren, restaurant, gym, pool, enz.

In dit gebruiksgeval, zullen wij zien hoe te om een gepersonaliseerd bericht in real time naar een persoon te verzenden die naast een baken loopt die dichtbij de spanwijdte wordt geplaatst.

We willen alleen een bericht sturen als de persoon een vrouw is. Het bericht moet binnen seconden worden ontvangen.

![](../assets/journeyuc1_16.png)

## Voorwaarden {#prerequisites}

Voor ons gebruik hebben we één e-mailsjabloon voor berichten voor transacties in Adobe Campaign Standard ontworpen. We gebruiken een berichtensjabloon voor een gebeurtenistransactie. Refer to this [page](https://docs.adobe.com/content/help/nl-NL/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard is geconfigureerd om e-mailberichten te verzenden.

De gebeurtenissen worden verzonden van de mobiele telefoon van de klanten wanneer zij dichtbij een baken worden ontdekt. U moet een mobiele toepassing ontwerpen om gebeurtenissen van de mobiele telefoon van de klant naar de mobiele SDK te verzenden.