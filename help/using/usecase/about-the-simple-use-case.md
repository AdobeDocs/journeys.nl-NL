---
product: adobe campaign
title: Eenvoudige gebruiksscenario's
description: Meer informatie over de reis, eenvoudig gebruik
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%

---

# Eenvoudige gebruiksscenario&#39;s{#concept_grh_vby_w2b}

## Doel {#purpose}

Laten we het voorbeeld nemen van een hotelmerk genaamd Marlton. In hun hotels hebben ze baken-apparaten in de buurt van alle strategische gebieden geplaatst: lobby, vloeren, restaurant, gym, pool, enz.

In dit gebruiksgeval, zullen wij zien hoe te om een gepersonaliseerd bericht in real time naar een persoon te verzenden die naast een baken loopt die dichtbij de spanwijdte wordt geplaatst.

We willen alleen een bericht sturen als de persoon een vrouw is. Het bericht moet binnen seconden worden ontvangen.

![](../assets/journeyuc1_16.png)

## Voorwaarden {#prerequisites}

Voor ons gebruik hebben we één e-mailsjabloon voor berichten voor transacties in Adobe Campaign Standard ontworpen. We gebruiken een berichtensjabloon voor een gebeurtenistransactie. Zie dit [page](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=nl).

Adobe Campaign Standard is geconfigureerd om e-mailberichten te verzenden.

De gebeurtenissen worden verzonden van de mobiele telefoon van de klanten wanneer zij dichtbij een baken worden ontdekt. U moet een mobiele toepassing ontwerpen om gebeurtenissen van de mobiele telefoon van de klant naar de mobiele SDK te verzenden.
