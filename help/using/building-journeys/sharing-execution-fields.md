---
product: adobe campaign
title: Velden voor het uitvoeren van acties van journeyStep-gebeurtenissen
description: Velden voor het uitvoeren van acties van journeyStep-gebeurtenissen
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 5%

---

# Velden voor het uitvoeren van acties van journeyStep-gebeurtenissen {#sharing-execution-fields}

Deze mixin wordt gedeeld door de tripStepEvent en tripStepProfileEvent.

Als in de stap een actie moet worden verwerkt, worden die velden toegevoegd aan de gebeurtenislading.

## actionID

Id van de handeling die wordt uitgevoerd.

Type: string

## actionName

Naam van de handeling. Als er geen naam is ingesteld, wordt de stepName uitgevoerd.

Type: string

## actionType

Type handeling.

Type: string

## actionParameterized

Hiermee wordt aangegeven of de handeling al dan niet wordt geparametriseerd.

Type: boolean

## actionExecutionTime

De hoeveelheid tijd (in milliseconden) die is besteed aan het uitvoeren van een huidige handeling.

Type: lang

## actionExecutionError

Type fout dat optreedt wanneer de handeling wordt aangeroepen.

Type: string

Waarden:
* http
* begrenzen
* timeout
* error

## actionExecutionErrorCode

Code voor uitvoeringsfout van handeling. Wordt weergegeven als de fout een code heeft, zoals een HTTP-code.

Type: string

## actionExecutionOriginError

Een time-out kan in twee gevallen optreden:

* bij de eerste poging wordt een handeling uitgevoerd. In dit geval is de uitvoering niet voltooid en is er geen onderliggende fout
* bij een nieuwe poging: in dit geval, beschrijft actionExecOrigError/actionExecOrigErrorCode de fout die op de poging alvorens wordt ontmoet opnieuw.

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

Type: string

## actionExecutionOriginCode

Foutcode van de actionExecOrigError.

Type: string

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

Type: string

## deliveryJobID

Dit beschrijft de identiteitskaart van de leveringstaak voor de partijreis.

Type: string

## batchDeliveryID

Dit beschrijft leveringsId voor de partijreis.

Type: string

## fromSegmentTrigger

Dit beschrijft als de Reis van de Partij van het Segment van het Publiek wordt teweeggebracht.

Type: boolean

## actionSchedulerCount

Aantal verzoeken van het plannerbericht die naar de plannerdienst tijdens de stapverwerking worden verzonden.

Type: lang
