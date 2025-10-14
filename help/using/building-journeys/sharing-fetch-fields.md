---
product: adobe campaign
title: Velden voor het ophalen van gegevens van journeyStep-gebeurtenissen
description: Velden voor het ophalen van gegevens van journeyStep-gebeurtenissen
feature: Journeys
role: User
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 3%

---

# Velden voor het ophalen van gegevens van journeyStep-gebeurtenissen {#sharing-fetch-fields}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Deze mixin wordt gedeeld door de tripStepEvent en tripStepProfileEvent.

Tijdens een stapverwerking, kunnen wij geen gegevens halen op gebiedsgroepen.

## fetchTotalTime

Totale hoeveelheid tijd die in gegevens wordt doorgebracht halen in millis tijdens de stapverwerking.

Type: lang

## fetchTypeInError

Definieert of de fout Ophalen in zich op de Adobe Experience Platform of op een aangepaste gegevensbron bevindt.

Type: tekenreeks

Waarden:
* aep
* aangepast

## fetchError

Type fout dat gebeurt wanneer de gegevens worden opgehaald verwerkt.

Type: tekenreeks

Waarden:
* http
* begrenzen
* timedout
* fout

## fetchErrorCode

Code voor ophalen fout. Wordt weergegeven als de fout een code heeft, zoals een HTTP-code. Wanneer actionExecError bijvoorbeeld http is, vertegenwoordigt code 404 de HTTP 404-fout.

Type: tekenreeks

## fetchOriginError

Een time-out kan in twee gevallen optreden:

* bij de eerste poging wordt de handeling uitgevoerd. In dit geval is de uitvoering niet voltooid, dus is er geen onderliggende fout
* voor een nieuwe poging: in dit geval beschrijft actionExecOrigError/actionExecOrigErrorCode de fout die bij de poging vóór het opnieuw proberen wordt ontmoet.

Bijvoorbeeld, worden de gegevens gehaald van de Verenigde Dienst van het Profiel en HTTP 500 fout is teruggekeerd bij de eerste poging. De fetch wordt opnieuw geprobeerd, maar de duur van de 2 pogingen overschrijdt de onderbreking. Vervolgens wordt de uitvoering van de handeling gecodeerd als een time-out. Het actieonderdeel ziet er als volgt uit:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Type: tekenreeks

## fetchOriginErrorCode

De foutcode van het systeem [!DNL Journey Orchestration] vraagt. Het kan bijvoorbeeld een 404, 500, enzovoort zijn.

Type: tekenreeks

## fetchCount

Hoeveel keer worden de gegevens opgehaald, ongeacht het type bron.

Type: lang

## fetchPlatformTotalTime

De totale hoeveelheid tijd die nodig is om de gegevens van Adobe Experience Platform op te halen in millis. Opmerking: deze hoeveelheid tijd wordt berekend vanaf het tijdstip waarop de motor het verrijkingsevenement naar de verrijkingsdienst verzendt en de reactie ontvangt.

Type: lang

## fetchPlatformCount

Hoeveel keer worden de gegevens opgehaald uit Adobe Experience Platform.

Type: lang

## fetchCustomTotalTime

De hoeveelheid tijd die nodig is om de aangepaste gegevens op te halen in millis. Opmerking: deze hoeveelheid tijd wordt berekend vanaf het tijdstip waarop de motor de verrijkingsgebeurtenis naar de verrijkingsdienst verzendt en de reactie ontvangt

Type: lang

## fetchCustomCount

Hoeveel keer worden de douanegegevens gehaald van externe systemen.

Type: lang
