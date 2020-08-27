---
title: Documentatie-updates
description: Meer informatie over documentatie-updates
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
source-git-commit: 10d4fd57e9a801dab2310b2b511bf99cf1d9170a
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 80%

---


# Documentatie-updates

Deze pagina bevat een overzicht van alle documentatie-updates voor [!DNL Journey Orchestration].
U kunt ook de [!DNL Journey Orchestration] [Opmerkingen bij de release](../release-notes/release-notes.md) raadplegen.

## Augustus 2020 {#august-2020}

* Toegevoegde informatie over het sorteren en kiezen van de kolommen die in de lijst met segmenten moeten worden weergegeven. [Meer informatie](../building-journeys/segment-qualification-events.md)
* Er is informatie toegevoegd over de manier waarop de naam en id van een segment moeten worden gekopieerd nadat het segment is geselecteerd. [Meer informatie](../building-journeys/segment-qualification-events.md)
* Het aantal gevallen van Experience Platform is op de verschillende pagina&#39;s geharmoniseerd.

## Juli 2020 {#july-2020}

* Er is een koppeling toegevoegd naar een nieuwe zelfstudievideo over stapgebeurtenissen die rapporteren aan Adobe Experience Platform. [Meer informatie](../building-journeys/sharing-overview.md)
* De sectie van de gebeurtenisactiviteiten is gereorganiseerd in specifieke subsecties voor elk type van gebeurtenissen. [Meer informatie](../building-journeys/event-activities.md)
* Toegevoegde beste praktijken om overbelasting met segmentkwantificering te vermijden. [Meer informatie](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* Er is een notitie toegevoegd om uit te leggen hoe een reis moet worden voortgezet na een fout in een handeling of een voorwaarde. [Meer informatie](../about/troubleshooting.md#section_h3q_kqk_fhb)
* Er is een nieuwe sectie toegevoegd over de Alfa-functies die onder een beperkte groep klanten worden getest. [Meer informatie](../alpha/alpha-overview.md)
* Er is een nieuwe sectie toegevoegd over de integratie met Intelligent Services. [Meer informatie](../ai-services/ai-services-overview.md)
* Er is een nieuwe sectie toegevoegd over het maken van testprofielen. [Meer informatie](../building-journeys/testing-the-journey.md#create-test-profile)
* Er is informatie toegevoegd over het gebruik van de node **[!UICONTROL SegmentQualification]** in een journeyvoorwaarde of een actie. [Meer informatie](../building-journeys/segment-qualification-events.md)
* Er is een opmerking toegevoegd over transactionele berichten en de publicatie van gebeurtenissen in Campaign. Zie [Werken met Adobe Campaign](../action/working-with-adobe-campaign.md) en [Adobe Campaign-acties gebruiken](../building-journeys/using-adobe-campaign-actions.md).
* Er is informatie toegevoegd over de controles die worden uitgevoerd wanneer de URL van de Campaign Standard-instantie wordt getest. [Meer informatie](../action/working-with-adobe-campaign.md)
* Er is informatie toegevoegd over de compatibiliteit van reactiegebeurtenissen met Campaign Standard-instanties die worden gehost op AWS- of Azure-servers. [Meer informatie](../building-journeys/reaction-events.md)
* Er is een opmerking toegevoegd over de noodzaak om een beperkingsregel in te stellen wanneer u werkt met transactionele berichten in Campaign Standard. [Meer informatie](../action/working-with-adobe-campaign.md)
* Er is een opmerking toegevoegd over het genereren van echte gebeurtenissen bij het activeren van gebeurtenissen in de testmodus. [Meer informatie](../building-journeys/testing-the-journey.md#firing_events)

## Juni 2020 {#june-2020}

* Er is informatie toegevoegd over het aanpassen van de cachetermijn van de token voor een databron met aangepaste verificatie. [Meer informatie](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Updated screenshots and text to reflect the renaming of the **[!UICONTROL Finished]** journey state which has been changed to **[!UICONTROL Closed (no entrance)]**.
* Er is informatie toegevoegd over het definiëren van de taal voor de interface. [Meer informatie](../about/user-interface.md)
* De lijst met statussen van de journey van een gebruiker is verplaatst naar de sectie [Logboeken voor testmodus](../building-journeys/testing-the-journey.md#viewing_logs).

## April 2020 {#april-2020}

* Er is een nieuwe sectie toegevoegd over de definitie van het ervaringsgebeurtenisschema om gebruikers te helpen bij de configuratie van hun eerste gebeurtenis. [Meer informatie](../event/experience-event-schema.md)
* De startpagina voor [!DNL Journey Orchestration]-documentatie is bijgewerkt met aanvullende, handige koppelingen. [Meer informatie](../../journey-orchestration-home.md)

## Maart 2020 {#march-2020}

* Er zijn parameterbeschrijvingen toegevoegd voor _actionExecutionErrors_ en _fetchErrors_ in de sectie voor testlogboeken. [Meer informatie](../building-journeys/testing-the-journey.md#viewing_logs)
* De beperkingen voor aangepaste acties die tijdens een journey worden gebruikt, zijn bijgewerkt. You can also modify the **[!UICONTROL URL]** field and the **[!UICONTROL Authentication]** parameters. [Meer informatie](../action/about-custom-action-configuration.md)
* Er zijn nieuwe contextuele Help-items toegevoegd. Het deelvenster voor aangepaste payloadverificatie (bij acties en databronnen) bevat nu een Help-pictogram dat naar deze [sectie](../datasource/external-data-sources.md#section_wjp_nl5_nhb) verwijst.
* Gesloten journey’s kunnen nu worden gestopt. [Meer informatie](../building-journeys/using-the-journey-designer.md)
* De sectie met de interfacebeschrijving heeft een nieuwe lay-out. [Meer informatie](../about/user-interface.md)
* Het activeren van meerdere gebeurtenissen is toegevoegd aan de sectie over de testmodus [Meer informatie](../building-journeys/testing-the-journey.md#firing_events)
* The Test mode section has been updated regarding the new **[!UICONTROL Wait time in test]** parameter. [Meer informatie](../building-journeys/testing-the-journey.md)
* De sectie over testlogboeken is bijgewerkt met foutcodes en reacties met betrekking tot externe aanroepen. [Meer informatie](../building-journeys/testing-the-journey.md#viewing_logs)
* Tijdzonebeheer wordt nu centraal geregeld in het deelvenster voor journey-eigenschappen. Meer informatie leest u [hier](../building-journeys/changing-properties.md#timezone) en [hier](../building-journeys/timezone-management.md)
* De sectie over de journeyontwerper is bijgewerkt met recente verbeteringen. [Meer informatie](../building-journeys/using-the-journey-designer.md)
* De interfacebeschrijving is bijgewerkt met informatie over contextafhankelijke Help. [Meer informatie](../about/user-interface.md#section_ksq_zr1_ffb)
* Bij het bladeren door **XDM-velden** wordt nu de beschrijvende naam weergegeven. Verwante secties zijn bijgewerkt. [Meer informatie](../about/user-interface.md#friendly-names-display)

## Februari 2020 {#february-2020}

* De sneltoetssectie is bijgewerkt. Met de sneltoets **C** kunt u in alle lijstschermen een nieuw item maken. [Meer informatie](../about/user-interface.md#section_ksq_zr1_ffb)
* De overzichtspagina’s met [databronnen](../datasource/about-data-sources.md) en [acties](../action/action.md) zijn verbeterd.

## Januari 2020 {#january-2020}

* Er zijn beperkingen toegevoegd voor het ophalen van [ervaringsgebeurtenissen](../datasource/adobe-experience-platform-data-source.md) en [segmenten](../functions/functioninsegment.md).

<!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## December 2019 {#december-2019}

* Alle screenshots zijn bijgewerkt met interfacewijzigingen.
* De sectie over de testmodus is bijgewerkt. [Meer informatie](../building-journeys/testing-the-journey.md)
<!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).-->
* Gestandaardiseerde journey’s kunnen nu worden verwijderd. Gerelateerde documentatiepagina’s zijn bijgewerkt.
* Er worden nu twee kleuren weergegeven wanneer tijdens een journey problemen worden gedetecteerd. Rood voor fouten en oranje voor waarschuwingen. [Meer informatie](../about/troubleshooting.md)
* De sectie over de geavanceerde expressie-editor is bijgewerkt. [Meer informatie](../expression/expressionadvanced.md).
* De secties over [voorwaardelijke instructies](../expression/conditional-instruction.md) en [verzamelingsbeheer](../expression/collection-management-functions.md) zijn verplaatst en bijgewerkt.
* De sectie [functies](../expression/functions.md) is bijgewerkt met nieuwe voorbeelden.
* De documentatie over de [functie toDateTime](../functions/functiontodatetime.md) is bijgewerkt met syntaxiswijzigingen in tijdzones.
