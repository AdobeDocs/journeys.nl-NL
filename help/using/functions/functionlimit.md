---
product: adobe campaign
title: limiet
description: Meer informatie over de functielimiet
feature: Journeys
role: Developer
level: Experienced
exl-id: 7e006660-1206-4b8a-9e5b-c6fbeee9cc8f
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 3%

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

Retourneert `["A","B","C"]` .

`limit(["A", "B", "C", "D", "E"], 3, false)`

Retourneert `["C","D","E"]` .
