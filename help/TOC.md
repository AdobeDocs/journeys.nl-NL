---
product: Journeys
audience: end-user
user-guide-title: Journey Orchestration Help
index: true
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 1%

---


# [!DNL Journey Orchestration] Help {#using}

+ [Productdocumentatie](journey-orchestration-home.md)
+ Nieuwe functies {#release-notes}
   + [Opmerkingen bij de release](using/release-notes/release-notes.md)
   + [Documentatieupdates](using/release-notes/documentation-updates.md)
+ Beginnen met [!DNL Journey Orchestration] {#starting-with-journeys}
   + [Info [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Aan de slag](using/about/get-started.md)
   + [Gebruikersinterface](using/about/user-interface.md)
   + [Toegangsbeheer](using/about/access-management.md)
   + [Problemen oplossen](using/about/troubleshooting.md)
+ Een gebeurtenis configureren {#events-journeys}
   + [Gebeurtenissen](using/event/about-events.md)
   + [Over ExperienceEvent-schema&#39;s](using/event/experience-event-schema.md)
   + [De laadvelden definiëren](using/event/defining-the-payload-fields.md)
   + [De naamruimte selecteren](using/event/selecting-the-namespace.md)
   + [De gebeurtenistoets definiëren](using/event/defining-the-event-key.md)
   + [Een voorwaarde toevoegen](using/event/adding-a-condition.md)
   + [Een voorvertoning van de lading weergeven](using/event/previewing-the-payload.md)
   + [Aanvullende stappen om gebeurtenissen te verzenden](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ Een gegevensbron configureren {#data-source-journeys}
   + [Gegevensbronnen](using/datasource/about-data-sources.md)
   + [Veldgroepen](using/datasource/field-groups.md)
   + [Gegevensbron Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Externe gegevensbronnen](using/datasource/external-data-sources.md)
+ Een handeling configureren {#action-journeys}
   + [Handelingen](using/action/action.md)
   + [Werken met Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + Een systeem van derden gebruiken {#action-third-party}
      + [Aangepaste actieconfiguratie](using/action/about-custom-action-configuration.md)
      + [Beperkingen voor aangepaste handelingen](using/action/custom-action-limitations.md)
      + [URL-configuratie](using/action/url-configuration.md)
      + [De berichtparameters definiëren](using/action/defining-the-message-parameters.md)
+ Plaformuliersegmenten gebruiken {#configuring-segment}
   + [Informatie over segmenten van het platform](using/segment/about-segments.md)
   + [Een segment maken](using/segment/creating-a-segment.md)
   + [Segmenten in omstandigheden gebruiken](using/segment/using-a-segment.md)
+ Een reis maken {#building-journeys}
   + Informatie over het maken van reizen {#about-journey-building}
      + [Een reis maken](using/building-journeys/journey.md)
      + [De reisontwerper gebruiken](using/building-journeys/using-the-journey-designer.md)
      + [Eigenschappen wijzigen](using/building-journeys/changing-properties.md)
      + [Reisversies](using/building-journeys/journey-versions.md)
      + [Een reis beëindigen](using/building-journeys/terminating-a-journey.md)
      + [Tijdzonebeheer](using/building-journeys/timezone-management.md)
   + Activiteiten {#about-journey-building}
      + Gebeurtenisactiviteiten {#events-activities}
         + [Gebeurtenisactiviteiten](using/building-journeys/event-activities.md)
         + [Algemene gebeurtenissen](using/building-journeys/general-events.md)
         + [Gebeurtenissen van Reaction](using/building-journeys/reaction-events.md)
         + [Segmentkwalificatiegebeurtenissen](using/building-journeys/segment-qualification-events.md)
      + Orchestratie {#orchestration-activities}
         + [Informatie over orkestwerkzaamheden](using/building-journeys/about-orchestration-activities.md)
         + [Condition-activiteit](using/building-journeys/condition-activity.md)
         + [Eindactiviteit](using/building-journeys/end-activity.md)
         + [Wacht op activiteit](using/building-journeys/wait-activity.md)
      + Acties {#action-activities}
         + [Informatie over actieactiviteiten](using/building-journeys/about-action-activities.md)
         + [Adobe Campaign-handelingen gebruiken](using/building-journeys/using-adobe-campaign-actions.md)
         + [Aangepaste handelingen gebruiken](using/building-journeys/using-custom-actions.md)
   + [De reis testen](using/building-journeys/testing-the-journey.md)
   + [De reis publiceren](using/building-journeys/publishing-the-journey.md)
   + Reisstappen delen met Adobe Experience Platform {#sharing-journey-steps}
      + [Overzicht van stap delen voor reizen](using/building-journeys/sharing-overview.md)
      + [tripSteps-gebeurtenissen - gemeenschappelijke velden](using/building-journeys/sharing-common-fields.md)
      + [uitvoeringsvelden van handelingen voor gebeurtenissen van de tripStep](using/building-journeys/sharing-execution-fields.md)
      + [gegevens ophalen van gebeurtenissen van de tripStep velden](using/building-journeys/sharing-fetch-fields.md)
      + [identiteitsvelden van gebeurtenissen van de tripStep](using/building-journeys/sharing-identity-fields.md)
      + [reisvelden](using/building-journeys/sharing-journey-fields.md)
+ De geavanceerde expressie-editor gebruiken {#building-advanced-conditions-journeys}
   + [Over de geavanceerde expressie-editor](using/expression/expressionadvanced.md)
   + Syntaxis {#syntax}
      + [Algemeen](using/expression/generalities.md)
      + [Voorwaardelijke instructie](using/expression/conditional-instruction.md)
      + [Gegevenstypen](using/expression/data-types.md)
      + [Veldverwijzingen](using/expression/field-references.md)
      + [Verzamelbeheerfuncties](using/expression/collection-management-functions.md)
      + [Operatoren](using/expression/operators.md)
      + [Voorbeelden](using/expression/advanced-editor-use-cases.md)
   + Functies {#main-functions-journey}
      + [Hoofdfuncties](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [getBestSendTime](using/functions/functiongetbestsendtime.md)
         + [inSegment](using/functions/functioninsegment.md)
      + Samenvoeging {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [aantal](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [differentCount](using/functions/functiondistinctcount.md)
         + [differentCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [som](using/functions/functionsum.md)
      + Conversie {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Datum {#date}
         + [currentTime &#x200B; InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYear](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYear](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + Lijst {#list}
         + [onderscheiden](using/functions/functiondistinct.md)
         + [differentWithNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sorteren](using/functions/functionsort.md)
      + Math {#math}
         + [willekeurig](using/functions/functionrandom.md)
         + [rond](using/functions/functionround.md)
      + String {#string}
         + [concat](using/functions/functionconcat.md)
         + [bevatten](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lager](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [vervangen](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [bijsnijden](using/functions/functiontrim.md)
         + [bovenste](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Uw rapporten samenstellen{#journey-reports}
   + [Informatie over reisrapporten](using/reporting/about-journey-reports.md)
   + [Uw reisrapporten maken](using/reporting/creating-your-journey-reports.md)
   + [Metriek en afmetingen](using/reporting/metrics-and-dimensions.md)
+ Integratie met intelligente services{#use-case-advanced}
   + [Over AI-integratie](using/ai-services/ai-services-overview.md)
   + [Hefboomwerkings-AI](using/ai-services/leveraging-fatigue-scores.md)
   + [Levering van AI van Klant](using/ai-services/leveraging-customer-ai.md)
+ Gebruik hoofdletters{#use-cases-journeys}
   + Eenvoudig gebruik{#use-case-simple}
      + [Over het eenvoudige gebruik](using/usecase/about-the-simple-use-case.md)
      + [De gebeurtenis configureren](using/usecase/configuring-the-event.md)
      + [De gegevensbron configureren](using/usecase/configuring-the-data-source.md)
      + [De reis maken](using/usecase/simple-uc-building-the-journey.md)
   + Geval voor geavanceerd gebruik{#use-case-advanced}
      + [Over het geavanceerde gebruiksscenario](using/usecase/about-the-advanced-use-case.md)
      + [Gebeurtenissen configureren](using/usecase/configuring-the-events.md)
      + [De gegevensbronnen configureren](using/usecase/configuring-the-data-sources.md)
      + [De reis maken](using/usecase/building-the-journey.md)
+ Werken met API&#39;s{#working-with-apis}
   + [API&#39;s uitlijnen](using/api/capping.md)
+ Alfa-functies {#alpha}
   + [Overzicht van Alfa-functies](using/alpha/alpha-overview.md)
   + [Gebruikersinterface](using/alpha/alpha-interface.md)
   + [Segmenttriggeractiviteit](using/alpha/alpha-segment-trigger.md)
   + [Gebeurtenissen op basis van regels](using/alpha/alpha-events.md)

