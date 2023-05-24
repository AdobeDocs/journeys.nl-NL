---
product: adobe campaign
title: distinct
description: Meer informatie over de functie afzonderlijk
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 5%

---

# distinct {#distinct}

Geeft als resultaat de verschillende waarden of objecten van een bepaalde lijst. Null-items worden genegeerd.

## Categorie

Lijst

## Functiesyntaxis

`distinct(<parameters>)`

## Parameters

| Parameter | Type | Beschrijving |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly of listObject | Te verwerken lijst. Voor listObject moet dit een veldverwijzing zijn. |
| keyAttributeName | string | Deze parameter is optioneel en alleen voor listObject. Wanneer de parameter niet wordt opgegeven, wordt een object als gedupliceerd beschouwd wanneer alle kenmerken dezelfde waarden hebben. Anders wordt een object als gedupliceerd beschouwd wanneer het opgegeven kenmerk dezelfde waarde heeft. |

## Handtekeningen en geretourneerde typen

`distinct(<listInteger>)`

Retourneert een lijst met gehele getallen.

`distinct(<listDecimal>)`

Retourneert een lijst met decimalen.

`distinct(<listString>)`

Retourneert een lijst met tekenreeksen.

`distinct(<listDateTimeOnly>)`

Keert een lijst van datetimes zonder tijdzone terug te overwegen.

`distinct(<listDateTime>)`

Retourneert een lijst met datetimes.

`distinct(<listDateOnly>)`

Retourneert een lijst met datums.

`distinct(<listBoolean>)`

Retourneert een lijst met laarzen.

`distinct(<listDuration>)`

Retourneert een lijst met tijdsduur.

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

Retourneert een lijst met objecten.


## Voorbeelden

`distinct([10,2,10,null])`

Retourneert `[10, 2]`.
