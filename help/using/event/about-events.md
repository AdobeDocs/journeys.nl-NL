---
product: adobe campaign
title: Informatie over gebeurtenissen
description: Meer informatie over gebeurtenissen
feature: Journeys
role: User
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '446'
ht-degree: 100%

---

# Algemeen principe {#concept_gfj_fqt_52b}


>[!CAUTION]
>
>**Op zoek naar Adobe Journey Optimizer**? Klik [hier](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar verouderde materialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._



>[!CONTEXTUALHELP]
>id="jo_events"
>title="Informatie over gebeurtenissen"
>abstract="Een gebeurtenis is gekoppeld aan een persoon en Dit betreft het gedrag van een persoon of iets dat met een persoon is gekoppeld. Dit is waar [!DNL Journey Orchestration] op let tijdens journey’s om vervolgens de beste acties te orkestreren."

Een gebeurtenis is gekoppeld aan een persoon en Dit heeft betrekking op het gedrag van een persoon (een persoon heeft voorbeeld een product gekocht, een winkel bezocht, een website verlaten, enz.) of iets wat met een persoon in verband staat (een persoon heeft bijvoorbeeld 10.000 loyaliteitspunten bereikt). Dit is waar [!DNL Journey Orchestration] op let tijdens journey’s om vervolgens de beste acties te orkestreren.

Deze configuratie is **verplicht**, aangezien [!DNL Journey Orchestration] is ontworpen om naar gebeurtenissen te luisteren, en wordt altijd uitgevoerd door een **technische gebruiker**.

Met de gebeurtenisconfiguratie kunt u de informatie definiëren die door [!DNL Journey Orchestration] als gebeurtenissen wordt ontvangen. U kunt verschillende gebeurtenissen gebruiken (in verschillende stappen van een journey) en verschillende journey’s kunnen dezelfde gebeurtenis gebruiken.

Als u een gebeurtenis bewerkt die in een concept- of live journey wordt gebruikt, kunt u alleen de naam en de beschrijving wijzigen of payloadvelden toevoegen. We hanteren een strikte beperking voor de bewerking of het opstellen van concept- of live journey’s om te voorkomen dat journey’s worden afgebroken.

U kunt twee typen gebeurtenissen definiëren:

* **Op regels gebaseerde** gebeurtenissen: dit type gebeurtenis genereert geen eventID. Door de eenvoudige expressie-editor te gebruiken bepaalt u eenvoudig een regel die door het systeem zal worden gebruikt om de relevante gebeurtenissen te identificeren die uw journeys zullen triggeren. Deze regel kan zijn gebaseerd op elk veld dat beschikbaar is in de gebeurtenispayload, bijvoorbeeld de locatie van het profiel of het aantal items dat is toegevoegd aan de winkelwagen van het profiel.

  >[!CAUTION]
  >
  >Een beperkingsregel wordt bepaald voor op regels gebaseerde gebeurtenissen. Deze beperkt het aantal gekwalificeerde gebeurtenissen dat een journey kan verwerken, tot 5000 per seconde voor een bepaalde organisatie (ORG). Dit komt overeen met Journey Orchestration SLA&#39;s. Zie deze [pagina](https://helpx.adobe.com/nl/legal/product-descriptions/journey-orchestration.html).

* **Door het systeem gegenereerde** gebeurtenissen: deze gebeurtenissen vereisen een eventID. Dit eventID-veld wordt automatisch gegenereerd wanneer de gebeurtenis wordt gemaakt. Het systeem dat de gebeurtenis pusht, moet geen ID genereren, het moet overgaan naar degene die in de voorvertoning van de payload beschikbaar is.

Journey Orchestration vereist dat gebeurtenissen worden gestreamd of gebundeld naar Adobe Experience Platform. Deze gegevens hoeven niet noodzakelijkerwijs naar het Real-Time Profile te gaan. Als u de gebeurtenissen wilt gebruiken voor segmentatie of opzoeken in een aparte journey, raden we u aan de dataset voor profiel in te schakelen.

Als u wilt leren hoe u een gebeurtenis maakt, raadpleegt u deze [pagina](../event/about-creating.md).
