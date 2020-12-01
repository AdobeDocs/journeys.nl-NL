---
product: adobe campaign
solution: Journey Orchestration
title: Informatie over gebeurtenissen
description: Meer informatie over gebeurtenissen
translation-type: tm+mt
source-git-commit: c66c09441f69e7026c60c37f87972e1e4ac9f7f8
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 54%

---


# Algemeen principe {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Informatie over gebeurtenissen"
>abstract="Een gebeurtenis is gekoppeld aan een persoon en heeft betrekking op het gedrag van een persoon (bijvoorbeeld: iemand heeft een product gekocht, een winkel bezocht, een website verlaten, enz.) of op iets dat verband houdt met een persoon (bijvoorbeeld: iemand heeft 10.000 loyaliteitspunten verdiend). Dit is waar [!DNL Journey Orchestration] op let tijdens journey’s om vervolgens de beste acties te orkestreren."

Een gebeurtenis is gekoppeld aan een persoon en heeft betrekking op het gedrag van een persoon (bijvoorbeeld: iemand heeft een product gekocht, een winkel bezocht, een website verlaten, enz.) of op iets dat verband houdt met een persoon (bijvoorbeeld: iemand heeft 10.000 loyaliteitspunten verdiend). Dit is waar [!DNL Journey Orchestration] op let tijdens journey’s om vervolgens de beste acties te orkestreren.

Deze configuratie is **verplicht**, aangezien [!DNL Journey Orchestration] is ontworpen om naar gebeurtenissen te luisteren, en wordt altijd uitgevoerd door een **technische gebruiker**.

Met de gebeurtenisconfiguratie kunt u de informatie definiëren die door [!DNL Journey Orchestration] als gebeurtenissen wordt ontvangen. U kunt verschillende gebeurtenissen gebruiken (in verschillende stappen van een journey) en verschillende journey’s kunnen dezelfde gebeurtenis gebruiken.

Als u een gebeurtenis bewerkt die in een concept- of live journey wordt gebruikt, kunt u alleen de naam en de beschrijving wijzigen of payloadvelden toevoegen. We hanteren een strikte beperking voor de bewerking of het opstellen van concept- of live journey’s om te voorkomen dat journey’s worden afgebroken.

U kunt twee typen gebeurtenissen definiëren:

* **Op regels gebaseerde** gebeurtenissen: dit type gebeurtenis genereert geen eventID. Gebruikend de eenvoudige uitdrukkingsredacteur, bepaalt u eenvoudig een regel die door het systeem zal worden gebruikt om de relevante gebeurtenissen te identificeren die uw reizen zullen teweegbrengen. Deze regel kan worden gebaseerd op elk veld dat beschikbaar is in de gebeurtenislading, bijvoorbeeld de locatie van het profiel of het aantal items dat is toegevoegd aan het winkelwagentje van het profiel.

   >[!CAUTION]
   >
   >Een afschilderingsregel wordt bepaald voor op regel-gebaseerde gebeurtenissen. Het beperkt het aantal gekwalificeerde gebeurtenissen dat een reis kan verwerken tot 400 k per minuut. Neem contact op met het contactpunt voor het alpha-programma voor meer informatie. Naast deze plafondregel wordt een limiet van 5000 gebeurtenissen voor seconden gedefinieerd op het niveau van de reis.

* **Door het systeem gegenereerde** gebeurtenissen: deze gebeurtenissen vereisen een eventID. Dit veld eventID wordt automatisch gegenereerd wanneer de gebeurtenis wordt gemaakt. Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten overgaan beschikbaar in de voorproef van de lading.

Raadpleeg deze [pagina](../event/about-creating.md)voor meer informatie over het maken van een gebeurtenis.

