---
product: adobe campaign
title: limiet
description: Meer informatie over de functielimiet
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 4%

---

# limiet {#limit}

Retourneert de eerste of laatste N-elementen van een lijst.

## Categorie

Lijst

## Functiesyntaxis

`limit(<parameters>)`

## Parameters

| Parameter | Type | Beschrijving |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly of listObject | Te sorteren lijst. Voor listObject moet dit een veldverwijzing zijn. |
| numberOfItems | integer | Aantal items dat moet worden geretourneerd uit de opgegeven lijst. |
| firstOrLastItems | boolean | Deze parameter is optioneel (standaard true). true retourneert de eerste items. false retourneert de laatste items. |

## Handtekening en type geretourneerd

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

Retourneert een lijst met tekenreeksen.

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

Retourneert een lijst met gehele getallen.

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

Retourneert een lijst met decimalen.

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

Retourneert een lijst met laarzen.

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

Retourneert een lijst met datums.

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Keert een lijst van datetimes zonder tijdzone terug te overwegen.

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

Retourneert een lijst met datetimes.

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

Retourneert een lijst met tijdsduur.

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

Retourneert een lijst met objecten.

## Voorbeeld

`limit(["A", "B", "C", "D", "E"], 3)`

Retourneert `["A","B","C"]`.

`limit(["A", "B", "C", "D", "E"], 3, false)`

Retourneert `["C","D","E"]`.
