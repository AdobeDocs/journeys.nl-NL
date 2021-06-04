---
product: adobe campaign
user-guide-title: Journey Orchestration
title: Journey Orchestration-handleiding
user-guide-description: Verstrekt stapsgewijze instructies voor het implementeren en samenstellen van journeys.
index: true
feature: Journeys
source-git-commit: c49908d36ecbc68ae11b5621305f39dd59c67871
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 97%

---


# [!DNL Journey Orchestration]-handleiding  {#using}

+ [Productdocumentatie](journey-orchestration-home.md)
+ Nieuwe functies {#release-notes}
   + [Release-opmerkingen](using/release-notes/release-notes.md)
   + [Documentatie-updates](using/release-notes/documentation-updates.md)
+ Beginnen met [!DNL Journey Orchestration] {#starting-with-journeys}
   + [ [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Beperkingen](using/about/limitations.md)
   + [Aan de slag](using/about/get-started.md)
   + [Gebruikersinterface](using/about/user-interface.md)
   + [Toegangscontrole](using/about/access-management.md)
   + [Problemen oplossen](using/about/troubleshooting.md)
   + [Integratie met externe systemen](using/about/external-systems.md)
+ Een gebeurtenis configureren {#events-journeys}
   + Informatie over gebeurtenissen {#about-events}
      + [Algemeen principe](using/event/about-events.md)
      + [Datacyclus](using/event/about-data-cycle.md)
      + [Een gebeurtenis maken](using/event/about-creating.md)
      + [Adobe Analytics gebruiken](using/event/about-analytics.md)
      + [Informatie over ExperienceEvent-schema’s](using/event/experience-event-schema.md)
      + [Aanvullende stappen om gebeurtenissen te verzenden](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
   + [Payloadvelden definiëren](using/event/defining-the-payload-fields.md)
   + [Naamruimte selecteren](using/event/selecting-the-namespace.md)
   + [Gebeurtenistoets definiëren](using/event/defining-the-event-key.md)
   + [Voorwaarde toevoegen](using/event/adding-a-condition.md)
   + [Voorvertoning van de payload weergeven](using/event/previewing-the-payload.md)
+ Databron configureren {#data-source-journeys}
   + [Informatie over databronnen](using/datasource/about-data-sources.md)
   + [Veldengroepen](using/datasource/field-groups.md)
   + [Adobe Experience Platform-databron](using/datasource/adobe-experience-platform-data-source.md)
   + [Externe databronnen](using/datasource/external-data-sources.md)
+ Een actie configureren {#action-journeys}
   + [Acties](using/action/action.md)
   + [Werken met Adobe Campaign](using/action/working-with-adobe-campaig.md)
   + Een extern systeem gebruiken {#action-third-party}
      + [Informatie over het configureren van aangepaste acties](using/action/about-custom-action-configuration.md)
      + [URL-configuratie](using/action/url-configuration.md)
      + [Berichtparameters definiëren](using/action/defining-the-message-parameters.md)
+ Platformsegmenten gebruiken {#configuring-segment}
   + [Informatie over platformsegmenten](using/segment/about-segments.md)
   + [Segment maken](using/segment/creating-a-segment.md)
   + [Segmenten gebruiken in voorwaarden](using/segment/using-a-segment.md)
+ Een journey samenstellen{#building-journeys}
   + Journey’s samenstellen {#about-journey-building}
      + [Een journey maken](using/building-journeys/journey.md)
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
         + [Informatie over orkestratieactiviteiten](using/building-journeys/about-orchestration-activities.md)
         + [Voorwaardeactiviteit](using/building-journeys/condition-activity.md)
         + [Eindactiviteit](using/building-journeys/end-activity.md)
         + [Wachtactiviteit](using/building-journeys/wait-activity.md)
      + Actieactiviteiten {#action-activities}
         + [Actieactiviteiten](using/building-journeys/about-action-activities.md)
         + [Adobe Campaign-acties gebruiken](using/building-journeys/using-adobe-campaign-actions.md)
         + [Aangepaste acties gebruiken](using/building-journeys/using-custom-actions.md)
         + [Van de ene journey naar de andere gaan](using/building-journeys/jump.md)
         + [Profiel bijwerken](using/building-journeys/update-profiles.md)
   + [Journey testen](using/building-journeys/testing-the-journey.md)
   + [Journey publiceren](using/building-journeys/publishing-the-journey.md)
   + Journeystappen delen met Adobe Experience Platform {#sharing-journey-steps}
      + [Overzicht van het delen van journeystappen](using/building-journeys/sharing-overview.md)
      + [journeySteps-gebeurtenissen - gemeenschappelijke velden](using/building-journeys/sharing-common-fields.md)
      + [journeyStep-gebeurtenissen - velden voor het uitvoeren van acties](using/building-journeys/sharing-execution-fields.md)
      + [journeyStep-gebeurtenissen - velden voor het ophalen van data](using/building-journeys/sharing-fetch-fields.md)
      + [journeyStep-gebeurtenissen - identiteitsvelden](using/building-journeys/sharing-identity-fields.md)
      + [journeyvelden](using/building-journeys/sharing-journey-fields.md)
+ De geavanceerde expressie-editor gebruiken {#building-advanced-conditions-journeys}
   + [De geavanceerde expressie-editor](using/expression/expressionadvanced.md)
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
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Datum {#date}
         + [currentTime&#x200B;InMillis](using/functions/functioncurrenttimeinmillis.md)
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
      + Lijst {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [getListItem](using/functions/functiongetlistitem.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + Wiskundig {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Tekenreeks {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
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
   + [Cijfers en dimensies](using/reporting/metrics-and-dimensions.md)
+ Integratie met Intelligent Services{#use-case-advanced}
   + [AI-integratie](using/ai-services/ai-services-overview.md)
   + [Klant-AI gebruiken](using/ai-services/leveraging-customer-ai.md)
+ Gebruiksscenario’s{#use-cases-journeys}
   + Een gepersonaliseerde e-mail verzenden{#use-case-simple}
      + [Informatie over eenvoudige gebruiksscenario&#39;s](using/usecase/about-the-simple-use-case.md)
      + [De gebeurtenis configureren](using/usecase/configuring-the-event.md)
      + [De databron configureren](using/usecase/configuring-the-data-source.md)
      + [De journey samenstellen](using/usecase/simple-uc-building-the-journey.md)
   + Een cross-channel journey maken{#use-case-advanced}
      + [Informatie over geavanceerde gebruiksscenario&#39;s](using/usecase/about-the-advanced-use-case.md)
      + [Gebeurtenissen configureren](using/usecase/configuring-the-events.md)
      + [Databronnen configureren](using/usecase/configuring-the-data-sources.md)
      + [De journey samenstellen](using/usecase/building-the-journey.md)
   + [Een bericht verzenden met Campaign Classic](using/usecase/campaign-v7-v8-use-case.md)
+ Werken met API’s{#working-with-apis}
   + [API’s beperken](using/api/capping.md)
