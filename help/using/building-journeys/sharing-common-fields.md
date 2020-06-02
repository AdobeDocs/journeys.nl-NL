---
title: journaalgebeurtenissen gemeenschappelijke velden
description: journaalgebeurtenissen gemeenschappelijke velden
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
source-git-commit: 10402a774bda66629f30869102d5e6ceca267535
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 0%

---


# journaalgebeurtenissen gemeenschappelijke velden {#sharing-common-fields}

Deze mixin wordt gedeeld door de tripStepEvent en tripStepProfileEvent.

Dit zijn de algemene XDM-velden die de Journey Orchestration naar het Adobe-gegevensplatform verzendt. Voor elke stap die op reis wordt verwerkt, worden gemeenschappelijke velden verzonden. Voor aangepaste handelingen en verbeteringen worden specifiekere velden gebruikt.

Sommige van deze velden zijn alleen beschikbaar in specifieke verwerkingspatronen (uitvoering van handelingen, ophalen van gegevens, enz.) om de omvang van gebeurtenissen te beperken.

## ingang

Geeft aan of de gebruiker de reis heeft betreden. Als dit niet het geval is, gaan we ervan uit dat de waarde onwaar is.

Type: boolean

Waarden: true/false

## intrede

Geeft aan of de gebruiker de reis opnieuw is gestart met hetzelfde exemplaar. Als dit niet het geval is, gaan we ervan uit dat de waarde onwaar is.

Type: boolean

Waarden: true/false

## instanceEnded

Geeft aan of de instantie is beëindigd (geslaagd of niet).

Type: boolean

## eventID

Gebeurtenis-id tijdens de verwerking, voor de stapverwerking. Als de gebeurtenis een externe gebeurtenis is, is de waarde eventId. Als de gebeurtenis een interne gebeurtenis is, is de waarde de interne eventId (zoals scheduledNotificationReceived, executedAction, enz.).

Type: string

## nodeID

Client node id (vanaf het canvas).

Type: string

## stepID

Unieke id van de stap die momenteel wordt verwerkt.

Type: string

## stepName

Naam van de stap die momenteel wordt verwerkt.

Type: string

## stepType

Type van de stap.

Type: string

Mogelijke waarden:

* Voorwaarde
* Handeling
* Planner
* Timer

## stepStatus

Status van de stap die de status van de stap vertegenwoordigt, wanneer de verwerking ervan is uitgevoerd (en de stapgebeurtenis is geactiveerd).

Type: string

De status kan zijn:

* beëindigd: de stap heeft geen overgang en de verwerking ervan is voltooid.
* fout: er is een fout opgetreden tijdens de stapverwerking.
* overgangen: de stap wacht op een gebeurtenis om over te gaan naar een andere stap.
* beperkt: de stap is mislukt op een begrenzingsfout die tijdens een handeling of verrijking is opgetreden.
* timedout: de stap is mislukt op een time-outfout die tijdens een handeling of verrijking is opgetreden.
* instanceTimeout: de stap heeft de verwerking gestopt, omdat de instantie de time-out heeft bereikt.

## tripID

ID van de reis.

Type: string

## tripVersionID

ID van de reisversie. Deze id vertegenwoordigt de identiteitsverwijzing naar de reis, in het geval van de tripStepEvent.

Type: string

## tripVersionName

Naam van de reisversie.

Type: string

## tripVersion

Versie van de reisversie.

Type: string

## instanceID

Interne id van het reisexemplaar.

Type: string

## externalKey

Externe sleutel die uit de gebeurtenis is geëxtraheerd om deze te verwerken.

Type: string

## parentStepID

Stap-id van het bovenliggende element van de huidige verwerkte stap in de instantie.

Type: string

## parentStepName

De naam van de stap van het bovenliggende element van de huidige stap.

Type: string

## parentTransitionID

Id van de overgang die de instantie naar de verwerkte stap heeft gebracht.

Type: string

## parentTransitionName

Naam van de overgang die de instantie aan de verwerkte stap heeft gebracht.

Type: string

## inTest

Vermeld of deze reis in testmodus staat of niet.

Type: boolean

## processingTime

Totale hoeveelheid tijd in milliseconden van de ingang van de instantiestappen aan het eind van de verwerking.

Type: lang

## instanceType

Hiermee wordt het instantietype aangegeven als het een batch of eenheidsinstantie is.

Type: string

Waarden: partij/eenheid

## recienceIndex

Index van de herhaling als de reis partij en terugkerend is (eerste looppas heeft terugkerendIndex = 1).

Type: lang

## isBatchToUnitary

Geeft aan of deze eenheidsinstantie is geactiveerd door een batchinstantie.

Type: boolean

## batchExternalKey

External Key for batch event.

Type: string

## batchInstanceID

this is the batch instance ID.

Type: string

## batchUnitaryBranchID

als de instantie is geactiveerd door een batchinstantie, is dit de eenheidvertakkings-id.

Type: string