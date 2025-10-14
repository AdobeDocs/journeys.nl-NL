---
product: adobe campaign
title: journaalgebeurtenissen - gemeenschappelijke velden
description: journaalgebeurtenissen - gemeenschappelijke velden
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 0%

---

# journaalgebeurtenissen - gemeenschappelijke velden {#sharing-common-fields}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Deze mixin wordt gedeeld door de tripStepEvent en tripStepProfileEvent.

Dit zijn de algemene XDM-velden die [!DNL Journey Orchestration] naar Adobe Experience Platform verzendt. Voor elke stap die op reis wordt verwerkt, worden gemeenschappelijke velden verzonden. Voor aangepaste handelingen en verbeteringen worden specifiekere velden gebruikt.

Sommige van deze velden zijn alleen beschikbaar in specifieke verwerkingspatronen (het uitvoeren van handelingen, het ophalen van gegevens, enz.) om de grootte van gebeurtenissen te beperken.

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

Type: tekenreeks

## nodeID

Client node id (vanaf het canvas).

Type: tekenreeks

## stepID

Unieke id van de stap die momenteel wordt verwerkt.

Type: tekenreeks

## stepName

Naam van de stap die momenteel wordt verwerkt.

Type: tekenreeks

## stepType

Type van de stap.

Type: tekenreeks

Mogelijke waarden:

* Voorwaarde
* Actie
* Planner
* Timer

## stepStatus

Status van de stap die de status van de stap vertegenwoordigt, wanneer de verwerking ervan is uitgevoerd (en de stapgebeurtenis is geactiveerd).

Type: tekenreeks

De status kan zijn:

* beëindigd: de stap heeft geen overgang en zijn verwerking is met succes geëindigd.
* fout: er is een fout opgetreden tijdens de stapverwerking.
* overgangen: de stap wacht op een gebeurtenis om naar een andere stap over te gaan.
* beperkt: de stap is mislukt op een afkapfout die tijdens een handeling of verrijking is opgetreden.
* timeout: de stap is mislukt op een time-outfout die tijdens een handeling of verrijking is opgetreden.
* instanceTimeout: de stap heeft zijn verwerking tegengehouden, omdat de instantie zijn onderbreking heeft bereikt.

## tripID

ID van de reis.

Type: tekenreeks

## tripVersionID

ID van de reisversie. Deze id vertegenwoordigt de identiteitsverwijzing naar de reis, in het geval van de tripStepEvent.

Type: tekenreeks

## tripVersionName

Naam van de reisversie.

Type: tekenreeks

## tripVersion

Versie van de reisversie.

Type: tekenreeks

## instanceID

Interne id van het reisexemplaar.

Type: tekenreeks

## externalKey

Externe sleutel die uit de gebeurtenis is geëxtraheerd om deze te verwerken.

Type: tekenreeks

## parentStepID

Stap-id van het bovenliggende element van de huidige verwerkte stap in de instantie.

Type: tekenreeks

## parentStepName

De naam van de stap van het bovenliggende element van de huidige stap.

Type: tekenreeks

## parentTransitionID

Id van de overgang die de instantie naar de verwerkte stap heeft gebracht.

Type: tekenreeks

## parentTransitionName

Naam van de overgang die de instantie aan de verwerkte stap heeft gebracht.

Type: tekenreeks

## inTest

Vermeld of deze reis in testmodus staat of niet.

Type: boolean

## processingTime

Totale hoeveelheid tijd in milliseconden van de ingang van de instantiestappen aan het eind van de verwerking.

Type: lang

## instanceType

Hiermee wordt het instantietype aangegeven als het een batch of eenheidsinstantie is.

Type: tekenreeks

Waarden: batch/eenheidsprijs

## recienceIndex

Index van de herhaling als de reis partij en terugkerend is (eerste looppas heeft terugkerendIndex = 1).

Type: lang

## isBatchToUnitary

Geeft aan of deze eenheidsinstantie is geactiveerd door een batchinstantie.

Type: boolean

## batchExternalKey

External Key for batch event.

Type: tekenreeks

## batchInstanceID

this is the batch instance ID.

Type: tekenreeks

## batchUnitaryBranchID

als de instantie is geactiveerd door een batchinstantie, is dit de eenheidvertakkings-id.

Type: tekenreeks
