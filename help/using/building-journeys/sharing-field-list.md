---
title: Lijst met gebeurtenisvelden voor stappen
description: Lijst met gebeurtenisvelden voor stappen
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: b7568080-b88c-415c-9d3f-cc1361664838
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 5%

---

# Lijst met gebeurtenisvelden voor stappen {#sharing-field-list}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


De gebeurtenisgebieden van de stap worden georganiseerd door categorie.

* Informatievelden voor foutopsporing
* Reisvelden
* Profielvelden
* Gebeurtenisvelden Service

## debugInfo

| Veldnaam | Type | Beschrijving |
|---|---|------------|
| requestId | String | De aanvraag-id die Journey Orchestration gebruikt om de stroom van een aanvraag te volgen. |

## reis

Deze veldgroep wordt gebruikt in het reisschema (met betrekking tot tripStepEvent). Het bevat de volgende velden:

| Veldnaam | Type | Beschrijving |
|---|---|------------|
| ID | String | Identificatiecode voor de opgegeven reis |
| VersionID | String | Id van de reisversie. Deze id vertegenwoordigt de identiteit van een reis |
| name | String | Naam van de reis |
| beschrijving | String | Beschrijving van de reis |
| versie | String | versie, weergegeven als `major`.`minor` |

## profiel

Deze veldgroep is specifiek voor tripStepEvent: deze gebeurtenis heeft betrekking op de reis en heeft niet de identityMap, die de profielidentiteit beschrijft, als om het even welk.

Voor tripStepEvent, moeten wij gebieden met betrekking tot de identiteit ook toevoegen:

| Veldnaam | Type | Beschrijving |
|---|---|------------|
| ID | String | De profiel-id identificeert het profiel dat tijdens een reis is verzonden/gebruikt. Bijvoorbeeld: foo@adobe.com. |
| namespace | String | In dit veld wordt de naamruimte beschreven waarnaar wordt verwezen door het profiel dat wordt gebruikt in Journey. Bijvoorbeeld e-mail, ECID |

## serviceEvents

Deze mix bevat alle velden die overeenkomen met een profielexporttaak.

| Veldnaam | Type | Beschrijving |
|---|---|------------|
| ID | String | De id van de getriggerde segmentexporttaak |
| status | String | De status van de segmentexporttaak: in de wachtrij geplaatst, gestart, voltooid |
| exportCountTotal | Geheel | De maximaal mogelijke waarde van de segmentexporttaak |
| exportCountRealized | Geheel | Het werkelijke aantal segmenten dat via de taak is geëxporteerd |
| exportCountFailed | Geheel | Het aantal segmenten is mislukt tijdens het exporteren via de taak |
| exportSegmentID | String | De id van het segment dat wordt geëxporteerd |
| eventType | String | Het gebeurtenistype dat aangeeft of het een foutgebeurtenis in de info-gebeurtenis is: Info, Error |
| eventCode | String | De foutcode die de reden voor het overeenkomende eventType aangeeft |

## stepEvents

Deze categorie bevat de oorspronkelijke velden voor stapgebeurtenissen. Verwijs naar deze [ sectie ](../building-journeys/sharing-legacy-fields.md).
