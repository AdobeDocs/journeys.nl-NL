---
product: adobe campaign
title: Velden voor het uitvoeren van acties van journeyStep-gebeurtenissen
description: Velden voor het uitvoeren van acties van journeyStep-gebeurtenissen
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 4%

---

# Velden voor het uitvoeren van acties van journeyStep-gebeurtenissen {#sharing-execution-fields}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Deze mixin wordt gedeeld door de tripStepEvent en tripStepProfileEvent.

Als in de stap een actie moet worden verwerkt, worden die velden toegevoegd aan de gebeurtenislading.

## actionID

Id van de handeling die wordt uitgevoerd.

Type: tekenreeks

## actionName

Naam van de handeling. Als er geen naam is ingesteld, wordt de stepName uitgevoerd.

Type: tekenreeks

## actionType

Type handeling.

Type: tekenreeks

## actionParameterized

Hiermee wordt aangegeven of de handeling al dan niet wordt geparametriseerd.

Type: boolean

## actionExecutionTime

De hoeveelheid tijd (in milliseconden) die is besteed aan het uitvoeren van een huidige handeling.

Type: lang

## actionExecutionError

Type fout dat optreedt wanneer de handeling wordt aangeroepen.

Type: tekenreeks

Waarden:
* http
* begrenzen
* timeout
* fout

## actionExecutionErrorCode

Fout bij uitvoeren van code voor handeling. Wordt weergegeven als de fout een code heeft, zoals een HTTP-code.

Type: tekenreeks

## actionExecutionOriginError

Een time-out kan in twee gevallen optreden:

* bij de eerste poging wordt een handeling uitgevoerd. In dit geval is de uitvoering niet voltooid, dus is er geen onderliggende fout
* voor een nieuwe poging: in dit geval beschrijft actionExecOrigError/actionExecOrigErrorCode de fout die bij de poging vóór het opnieuw proberen wordt ontmoet.

Er wordt bijvoorbeeld een e-mail verzonden en er wordt een HTTP 500-fout geretourneerd bij de eerste poging. De fetch wordt opnieuw geprobeerd, maar de duur van de 2 pogingen overschrijdt de onderbreking. Vervolgens wordt de uitvoering van de handeling gecodeerd als een time-out. Het actieonderdeel ziet er als volgt uit:

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

Type: tekenreeks

## actionExecutionOriginCode

Foutcode van de actionExecOrigError.

Type: tekenreeks

## actionBusinessType

Geeft het type actie aan.

Waarden:

* bouwen
* ACS-e-mail
* ACS SMS
* ACS Push
* klant
* Epsilon
* ...

Type: tekenreeks

## deliveryJobID

Dit beschrijft de identiteitskaart van de leveringstaak voor de partijreis.

Type: tekenreeks

## batchDeliveryID

Dit beschrijft leveringsId voor de partijreis.

Type: tekenreeks

## fromSegmentTrigger

Dit beschrijft als de Reis van de Partij van het Segment van het Publiek wordt teweeggebracht.

Type: boolean

## actionSchedulerCount

Aantal verzoeken van het plannerbericht die naar de plannerdienst tijdens de stapverwerking worden verzonden.

Type: lang
