---
title: Gebeurtenissen
description: Leer hoe u een gebeurtenis configureert
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Gebeurtenissen {#concept_gfj_fqt_52b}

Een gebeurtenis is gekoppeld aan een persoon. Het heeft betrekking op het gedrag van een persoon (bijvoorbeeld iemand heeft een product gekocht, een winkel bezocht, een website verlaten, enz.) of iets dat met een persoon verband houdt (een persoon bereikte bijvoorbeeld 10 000 loyaliteitspunten). Dit is waar Journey Orchestration naar zal luisteren tijdens reizen om de beste volgende acties te ordenen.

Deze configuratie is **verplicht**, aangezien de Orchestratie van de Reis wordt ontworpen om aan gebeurtenissen te luisteren, en altijd door een **technische gebruiker** wordt uitgevoerd.

De gebeurtenisconfiguratie staat u toe om de informatie te bepalen zal de Orchestratie van de Reis als gebeurtenissen ontvangen. U kunt verschillende gebeurtenissen gebruiken (in verschillende stappen van een reis) en verschillende reizen kunnen dezelfde gebeurtenis gebruiken.

Als u een gebeurtenis bewerkt die in een concept of live transport wordt gebruikt, kunt u alleen de naam, de beschrijving of ladingsvelden wijzigen. We beperken de uitgave van concept- of live reizen strikt om te voorkomen dat reizen worden afgebroken.

## Algemeen beginsel {#section_r1f_xqt_pgb}

Gebeurtenissen zijn POST API-aanroepen. Gebeurtenissen worden via de API&#39;s voor streaming-inname naar het Adobe Experience Cloud Data Platform verzonden. De URL-bestemming van gebeurtenissen die via transactie-API&#39;s worden verzonden, wordt een &quot;inlet&quot; genoemd. De nuttige lading van gebeurtenissen volgt het formatteren XDM.

De nuttige lading bevat informatie die door Streaming Ingestie-API&#39;s wordt vereist om te werken (in de koptekst) en de informatie die door de Journey Orchestration wordt vereist om te werken (de gebeurtenis-id, een deel van de lading) en informatie die tijdens reizen (in het lichaam, bijvoorbeeld, de hoeveelheid een verlaten karretje) moet worden gebruikt. Er zijn twee modi voor de streamingopname, geverifieerd en niet geverifieerd. Raadpleeg [deze koppeling](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md)voor meer informatie over Streaming Ingestie-API&#39;s.

Na aankomst door Streaming Ingestie APIs, stromen de gebeurtenissen in de interne dienst genoemd Pijpleiding en dan in het Platform van Gegevens. Als het gebeurtenisschema de markering van de Dienst van het Profiel van de Klant in real time toegelaten heeft en een dataset identiteitskaart die ook de vlag van het Profiel van de Klant in real time heeft, vloeit het in de Dienst van het Profiel van de Klant in real time.

De pijpleiding filtert gebeurtenissen die een nuttige lading hebben die Journey Orchestration eventIDs (zie het proces van de gebeurtenisverwezenlijking hieronder) bevat die door Journey Orchestration en in gebeurtenislading wordt verstrekt. Er wordt naar deze gebeurtenissen geluisterd door de Journey Orchestration en de bijbehorende reis wordt gestart.

## Een nieuwe gebeurtenis maken {#section_tbk_5qt_pgb}

Hier volgen de belangrijkste stappen voor het configureren van een nieuwe gebeurtenis:

1. Klik in het bovenste menu op het **[!UICONTROL Events]**tabblad. De lijst met gebeurtenissen wordt weergegeven. Zie[](../about/user-interface.md)voor meer informatie over de interface.

   ![](../assets/journey5.png)

1. Klik **[!UICONTROL Add]**om een nieuwe gebeurtenis te maken. Het deelvenster voor gebeurtenisconfiguratie wordt aan de rechterkant van het scherm geopend.

   ![](../assets/journey6.png)

1. Voer een naam in voor de gebeurtenis.

   >[!NOTE]
   >
   >Gebruik geen spaties of speciale tekens. Gebruik niet meer dan 30 tekens.

1. Voeg een beschrijving toe aan uw gebeurtenis. Deze stap is optioneel.
1. Definieer het schema en de payload velden: Dit is waar u de gebeurtenisinformatie (gewoonlijk genoemd een nuttige lading) selecteert de Orchestratie van de Reis verwacht om te ontvangen. U kunt deze informatie dan gebruiken tijdens uw reis. Zie [](../event/defining-the-payload-fields.md).
1. Het aantal reizen dat deze gebeurtenis gebruikt, wordt in het **[!UICONTROL Used in]**veld weergegeven. U kunt op het**[!UICONTROL View journeys]** pictogram klikken om de lijst met reizen weer te geven die deze gebeurtenis gebruiken.
1. Voeg een naamruimte toe. Deze stap is optioneel, maar wordt aangeraden als u een naamruimte toevoegt, zodat u gegevens die zijn opgeslagen in de realtime klantenprofielservice, kunt gebruiken. Het definieert het type sleutel van de gebeurtenis. Zie [](../event/selecting-the-namespace.md).
1. Definieer de sleutel: Kies een veld in uw payload-velden of definieer een formule om de persoon te identificeren die aan de gebeurtenis is gekoppeld. Deze sleutel wordt automatisch ingesteld (maar kan nog steeds worden bewerkt) als u een naamruimte selecteert. De reisorganisatie kiest dan ook de sleutel die moet overeenkomen met de naamruimte (als u bijvoorbeeld een naamruimte voor e-mail selecteert, wordt de e-mailsleutel geselecteerd). Zie [](../event/defining-the-event-key.md).
1. Voeg een voorwaarde toe. Deze stap is optioneel. Hierdoor kan het systeem alleen de gebeurtenissen verwerken die aan de voorwaarde voldoen. De voorwaarde kan alleen worden gebaseerd op informatie in de gebeurtenis. Zie [](../event/adding-a-condition.md).
1. Klik **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   De gebeurtenis is nu gevormd en klaar om in een reis worden gelaten vallen. Aanvullende configuratiestappen zijn vereist om gebeurtenissen te ontvangen. Zie [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
