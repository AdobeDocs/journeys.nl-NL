---
product: adobe campaign
title: Informatie over gebeurtenissen
description: Meer informatie over gebeurtenissen
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 78c758c75825c0f85788190c4526fa5c743c6673
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 87%

---

# Algemeen principe {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Informatie over gebeurtenissen"
>abstract="Een gebeurtenis is gekoppeld aan een persoon en Dit betreft het gedrag van een persoon of iets dat met een persoon is gekoppeld. Dit is waar [!DNL Journey Orchestration] op let tijdens journey’s om vervolgens de beste acties te orkestreren."

Een gebeurtenis is gekoppeld aan een persoon en heeft betrekking op het gedrag van een persoon (bijvoorbeeld: iemand heeft een product gekocht, een winkel bezocht, een website verlaten, enz.) of op iets dat verband houdt met een persoon (bijvoorbeeld: iemand heeft 10.000 loyaliteitspunten verdiend). Dit is waar [!DNL Journey Orchestration] op let tijdens journey’s om vervolgens de beste acties te orkestreren.

Deze configuratie is **verplicht**, aangezien [!DNL Journey Orchestration] is ontworpen om naar gebeurtenissen te luisteren, en wordt altijd uitgevoerd door een **technische gebruiker**.

Met de gebeurtenisconfiguratie kunt u de informatie definiëren die door [!DNL Journey Orchestration] als gebeurtenissen wordt ontvangen. U kunt verschillende gebeurtenissen gebruiken (in verschillende stappen van een journey) en verschillende journey’s kunnen dezelfde gebeurtenis gebruiken.

Als u een gebeurtenis bewerkt die in een concept- of live journey wordt gebruikt, kunt u alleen de naam en de beschrijving wijzigen of payloadvelden toevoegen. We hanteren een strikte beperking voor de bewerking of het opstellen van concept- of live journey’s om te voorkomen dat journey’s worden afgebroken.

U kunt twee typen gebeurtenissen definiëren:

* **Op regels gebaseerde** gebeurtenissen: dit type gebeurtenis genereert geen eventID. Door de eenvoudige expressie-editor te gebruiken bepaalt u eenvoudig een regel die door het systeem zal worden gebruikt om de relevante gebeurtenissen te identificeren die uw journeys zullen triggeren. Deze regel kan zijn gebaseerd op elk veld dat beschikbaar is in de gebeurtenispayload, bijvoorbeeld de locatie van het profiel of het aantal items dat is toegevoegd aan de winkelwagen van het profiel.

   >[!CAUTION]
   >
   >Een beperkingsregel wordt bepaald voor op regels gebaseerde gebeurtenissen. Deze beperkt het aantal gekwalificeerde gebeurtenissen dat een journey kan verwerken, tot 5000 per seconde voor een bepaalde organisatie (ORG). Dit komt overeen met Journey Orchestration SLA&#39;s. Zie deze [pagina](https://helpx.adobe.com/nl/legal/product-descriptions/journey-orchestration.html).

* **Door het systeem gegenereerde** gebeurtenissen: deze gebeurtenissen vereisen een eventID. Dit eventID-veld wordt automatisch gegenereerd wanneer de gebeurtenis wordt gemaakt. Het systeem dat de gebeurtenis pusht, moet geen ID genereren, het moet overgaan naar degene die in de voorvertoning van de payload beschikbaar is.

Journey Orchestration vereist dat gebeurtenissen worden gestreamd of gebatcheerd naar Adobe Experience Platform. Deze gegevens hoeven niet noodzakelijkerwijs naar het Real-Time Profiel te gaan. Als u de gebeurtenissen voor segmentatie of raadpleging in een afzonderlijke reis zou willen gebruiken, adviseren wij u toelaat de dataset voor profiel.

Als u wilt leren hoe u een gebeurtenis maakt, raadpleegt u deze [pagina](../event/about-creating.md).
