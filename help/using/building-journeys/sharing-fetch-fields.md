---
title: gegevens ophalen van gebeurtenissen van de tripStep velden
description: gegevens ophalen van gebeurtenissen van de tripStep velden
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---


# gegevens ophalen van gebeurtenissen van de tripStep velden {#sharing-fetch-fields}

Deze mixin wordt gedeeld door de tripStepEvent en tripStepProfileEvent.

Tijdens een stapverwerking, kunnen wij geen gegevens halen op gebiedsgroepen.

## fetchTotalTime

Totale hoeveelheid tijd die in gegevens wordt doorgebracht halen in millis tijdens de stapverwerking.

Type: lang

## fetchTypeInError

Definieert of de functie Ophalen in fout zich op het platform of op een aangepaste gegevensbron bevindt.

Type: string

Waarden:
* aep
* aangepast

## fetchError

Type fout dat gebeurt wanneer de gegevens worden opgehaald verwerkt.

Type: string

Waarden:
* http
* begrenzen
* timedout
* fout

## fetchErrorCode

Code voor ophalen fout. Wordt weergegeven als de fout een code heeft, zoals een HTTP-code. Wanneer actionExecError bijvoorbeeld http is, vertegenwoordigt code 404 de HTTP 404-fout.

Type: string

## fetchOriginError

Een time-out kan in twee gevallen optreden:

* bij de eerste poging wordt de handeling uitgevoerd. In dit geval is de uitvoering niet voltooid en is er geen onderliggende fout
* bij een nieuwe poging: in dit geval, beschrijft actionExecOrigError/actionExecOrigErrorCode de fout die op de poging alvorens wordt ontmoet opnieuw.

Bijvoorbeeld, worden de gegevens gehaald van de Verenigde Dienst van het Profiel en HTTP 500 fout is teruggekeerd bij de eerste poging. De fetch wordt opnieuw geprobeerd, maar de duur van de 2 pogingen overschrijdt de onderbreking. Vervolgens wordt de uitvoering van de handeling gecodeerd als een time-out. Het actieonderdeel ziet er als volgt uit:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Type: string

## fetchOriginErrorCode

De foutcode van het systeem [!DNL Journey Orchestration] vraagt. Het kan bijvoorbeeld een 404, 500, enzovoort zijn.

Type: string

## fetchCount

Hoeveel keer worden de gegevens opgehaald, ongeacht het type bron.

Type: lang

## fetchPlatformTotalTime

De totale hoeveelheid tijd die nodig is om de gegevens van het Data Platform in millis op te halen. Opmerking: deze hoeveelheid tijd wordt berekend vanaf het tijdstip waarop de motor de verrijkingsgebeurtenis naar de verrijkingsdienst verzendt en de reactie ontvangt .

Type: lang

## fetchPlatformCount

Hoeveel keer worden de gegevens opgehaald van Platform.

Type: lang

## fetchCustomTotalTime

De hoeveelheid tijd die nodig is om de aangepaste gegevens op te halen in millis. Opmerking: deze hoeveelheid tijd wordt berekend vanaf het tijdstip waarop de motor de verrijkingsgebeurtenis naar de verrijkingsdienst verzendt en de reactie ontvangt

Type: lang

## fetchCustomCount

Hoeveel keer worden de douanegegevens gehaald van externe systemen.

Type: lang
