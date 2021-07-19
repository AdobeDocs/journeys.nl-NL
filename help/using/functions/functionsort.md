---
product: adobe campaign
title: sort
description: Meer informatie over de functie sorteren
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 14%

---

# sorteren {#sort}

Sorteert een lijst met waarden in de natuurlijke volgorde. Het eerste argument is de lijst met waarden, het tweede is een booleaanse waarde die aangeeft of de sortering oploopt (true) of afneemt (false).

## Categorie

Lijst

## Functiesyntaxis

`sort(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| Lijst | listString |
| Lijst | listBoolean |
| Lijst | listInteger |
| Lijst | listDecimal |
| Lijst | listDuration |
| Lijst | listDateTime |
| Lijst | listDateTimeOnly |
| Boolean | Boolean |

## Handtekening en type geretourneerd

`sort(<listInteger>,<boolean>)`

Retourneert een lijst met gehele getallen.

`sort(<listDecimal>,<boolean>)`

Retourneert een lijst met decimalen.

`sort(<listString>,<boolean>)`

Retourneert een lijst met tekenreeksen.

`sort(<listDateTimeOnly>,<boolean>)`

Keert een lijst van datetimes zonder tijdzone terug te overwegen.

`sort(<listDateTime>,<boolean>)`

Retourneert een lijst met datetimes.

`sort(<listBoolean>,<boolean>)`

Retourneert een lijst met laarzen.

## Voorbeeld

`sort(["A", "C", "B"], true)`

Retourneert `["A","B","C"]`.

`sort([1, 3, 2], false)`

Retourneert `[3, 2, 1]`.
