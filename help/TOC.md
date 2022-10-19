---
product: adobe campaign
user-guide-title: Journey Orchestration
title: Journey Orchestration-handleiding
user-guide-description: Verstrekt stapsgewijze instructies voor het implementeren en samenstellen van journeys.
index: true
feature: Journeys
source-git-commit: 235992282b0a05873dc17984e044400dc8de1dd8
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 98%

---


# [!DNL Journey Orchestration] Gids  {#using}

+ [Productdocumentatie](journey-orchestration-home.md)
+ Nieuwe functies {#release-notes}
   + [Aanvullende informatie](using/release-notes/release-notes.md)
   + [Documentatie-updates](using/release-notes/documentation-updates.md)
   + [Upgrade naar Journey Optimizer](using/release-notes/upgrade-to-ajo.md)
+ Beginnen met [!DNL Journey Orchestration] {#starting-with-journeys}
   + [Over [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Beperkingen](using/about/limitations.md)
   + [Aan de slag](using/about/get-started.md)
   + [Gebruikersinterface](using/about/user-interface.md)
   + [Toegangsbeheer](using/about/access-management.md)
   + [Problemen oplossen](using/about/troubleshooting.md)
   + [Integratie met externe systemen](using/about/external-systems.md)
+ Een gebeurtenis configureren {#events-journeys}
   + Informatie over gebeurtenissen {#about-events}
      + [Algemeen principe](using/event/about-events.md)
      + [Datacyclus](using/event/about-data-cycle.md)
      + [Een gebeurtenis maken](using/event/about-creating.md)
      + [Adobe Analytics gebruiken](using/event/about-analytics.md)
      + [ExperienceEvent-schema’s](using/event/experience-event-schema.md)
      + [Aanvullende stappen om gebeurtenissen te verzenden](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
   + [Payloadvelden definiëren](using/event/defining-the-payload-fields.md)
   + [Naamruimte selecteren](using/event/selecting-the-namespace.md)
   + [Gebeurtenistoets definiëren](using/event/defining-the-event-key.md)
   + [Voorvertoning van de payload weergeven](using/event/previewing-the-payload.md)
+ Databron configureren {#data-source-journeys}
   + [Databronnen](using/datasource/about-data-sources.md)
   + [Veldgroepen](using/datasource/field-groups.md)
   + [Adobe Experience Platform-databron](using/datasource/adobe-experience-platform-data-source.md)
   + [Externe databronnen](using/datasource/external-data-sources.md)
+ Actie configureren {#action-journeys}
   + [Acties](using/action/action.md)
   + [Werken met Adobe Campaign Standard](using/action/working-with-adobe-campaign.md)
   + [Werken met Adobe Campaign v7/v8](using/action/acc-action.md)
   + Een systeem van derden gebruiken {#action-third-party}
      + [Aangepaste acties configureren](using/action/about-custom-action-configuration.md)
      + [URL-configuratie](using/action/url-configuration.md)
      + [Actieparameters definiëren](using/action/defining-the-message-parameters.md)
+ Segmenten gebruiken {#configuring-segment}
   + [Segmenten](using/segment/about-segments.md)
   + [Segment maken](using/segment/creating-a-segment.md)
   + [Segmenten gebruiken in voorwaarden](using/segment/using-a-segment.md)
+ Een journey samenstellen{#building-journeys}
   + Journey’s samenstellen {#about-journey-building}
      + [Journey maken](using/building-journeys/journey.md)
      + [Journeyontwerper gebruiken](using/building-journeys/using-the-journey-designer.md)
      + [Eigenschappen wijzigen](using/building-journeys/changing-properties.md)
      + [Journeyversies](using/building-journeys/journey-versions.md)
      + [Journey beëindigen](using/building-journeys/terminating-a-journey.md)
      + [Tijdzonebeheer](using/building-journeys/timezone-management.md)
      + [Testprofielen](using/building-journeys/creating-test-profiles.md)
   + Activiteiten {#about-journey-building}
      + Gebeurtenisactiviteiten {#events-activities}
         + [Gebeurtenisactiviteiten](using/building-journeys/event-activities.md)
         + [Algemene gebeurtenissen](using/building-journeys/general-events.md)
         + [Reactiegebeurtenissen](using/building-journeys/reaction-events.md)
         + [Segmentkwalificatiegebeurtenissen](using/building-journeys/segment-qualification-events.md)
      + Orkestratieactiviteiten {#orchestration-activities}
         + [Orkestratieactiviteiten](using/building-journeys/about-orchestration-activities.md)
         + [Voorwaardeactiviteit](using/building-journeys/condition-activity.md)
         + [Eindactiviteit](using/building-journeys/end-activity.md)
         + [Wachtactiviteit](using/building-journeys/wait-activity.md)
      + Actieactiviteiten {#action-activities}
         + [Actieactiviteiten](using/building-journeys/about-action-activities.md)
         + [Adobe Campaign Standard gebruiken](using/building-journeys/using-adobe-campaign-actions.md)
         + [Adobe Campaign v7/v8 gebruiken](using/building-journeys/using-adobe-campaign-classic.md)
         + [Aangepaste acties gebruiken](using/building-journeys/using-custom-actions.md)
         + [Van de ene journey naar de andere gaan](using/building-journeys/jump.md)
         + [Profiel bijwerken](using/building-journeys/update-profiles.md)
   + [Journey testen](using/building-journeys/testing-the-journey.md)
   + [Journey publiceren](using/building-journeys/publishing-the-journey.md)
   + Journeystappen delen met Adobe Experience Platform {#sharing-journey-steps}
      + [Overzicht van het delen van journeystappen](using/building-journeys/sharing-overview.md)
      + [Lijst met gebeurtenisvelden voor stappen](using/building-journeys/sharing-field-list.md)
      + Gebeurtenisvelden voor oudere stappen {#legacy-step-event-fields}
         + [Oudere velden](using/building-journeys/sharing-legacy-fields.md)
         + [Gemeenschappelijke velden van journeySteps-gebeurtenissen](using/building-journeys/sharing-common-fields.md)
         + [Velden voor het uitvoeren van acties van journeyStep-gebeurtenissen](using/building-journeys/sharing-execution-fields.md)
         + [Velden voor het ophalen van gegevens van journeyStep-gebeurtenissen](using/building-journeys/sharing-fetch-fields.md)
         + [Identiteitsvelden van journeyStep-gebeurtenissen](using/building-journeys/sharing-identity-fields.md)
         + [journeyvelden](using/building-journeys/sharing-journey-fields.md)
      + [Voorbeelden van query&#39;s](using/building-journeys/query-examples.md)
+ Expressies samenstellen {#building-advanced-conditions-journeys}
   + [Overzicht](using/expression/expressionadvanced.md)
   + Syntaxis {#syntax}
      + [Algemeen](using/expression/generalities.md)
      + [Voorwaardelijke instructie](using/expression/conditional-instruction.md)
      + [Datatypen](using/expression/data-types.md)
      + [Veldverwijzingen](using/expression/field-references.md)
      + [Functies voor het beheer van verzamelingen](using/expression/collection-management-functions.md)
      + [Operatoren](using/expression/operators.md)
      + [Journeyeigenschappen](using/expression/journey-properties.md)
      + [Voorbeelden](using/expression/advanced-editor-use-cases.md)
   + Functies {#main-functions-journey}
      + [Hoofdfuncties](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [inSegment](using/functions/functioninsegment.md)
      + Samenvoeging {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + Conversie {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateOnly](using/functions/functiontodateonly.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Datum {#date}
         + [currentTimeInMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
         + [updateTimeZone](using/functions/functionupdatetimezone.md)
      + Lijst {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [filter](using/functions/functionfilter.md)
         + [getListItem](using/functions/functiongetlistitem.md)
         + [in](using/functions/functionin.md)
         + [intersect](using/functions/functionintersect.md)
         + [limiet](using/functions/functionlimit.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + Wiskunde {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Tekenreeks {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [lengte](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notequalIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [split](using/functions/functionsplit.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Rapporten samenstellen{#journey-reports}
   + [Journeyrapporten](using/reporting/about-journey-reports.md)
   + [Journeyrapporten maken](using/reporting/creating-your-journey-reports.md)
   + [Statistieken en afmetingen](using/reporting/metrics-and-dimensions.md)
+ Integratie met Intelligent Services{#use-case-advanced}
   + [AI-integratie](using/ai-services/ai-services-overview.md)
   + [Klant-AI gebruiken](using/ai-services/leveraging-customer-ai.md)
+ Gebruiksscenario’s{#use-cases-journeys}
   + Een gepersonaliseerde e-mail verzenden{#use-case-simple}
      + [Eenvoudige gebruiksscenario&#39;s](using/usecase/about-the-simple-use-case.md)
      + [De gebeurtenis configureren](using/usecase/configuring-the-event.md)
      + [De databron configureren](using/usecase/configuring-the-data-source.md)
      + [Journey samenstellen](using/usecase/simple-uc-building-the-journey.md)
   + Een cross-channel journey maken{#use-case-advanced}
      + [Geavanceerde gebruiksscenario&#39;s](using/usecase/about-the-advanced-use-case.md)
      + [Gebeurtenissen configureren](using/usecase/configuring-the-events.md)
      + [Databronnen configureren](using/usecase/configuring-the-data-sources.md)
      + [Journey samenstellen](using/usecase/building-the-journey.md)
   + [Een bericht verzenden met Campaign v7/v8](using/usecase/campaign-classic-use-case.md)
   + [Verzamelingen dynamisch doorgeven met behulp van aangepaste acties](using/usecase/collections.md)
+ Werken met API’s{#working-with-apis}
   + [API’s beperken](using/api/capping.md)
