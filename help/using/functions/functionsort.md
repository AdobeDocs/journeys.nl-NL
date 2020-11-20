---
product: adobe campaign
solution: Journey Orchestration
title: sort
description: Meer informatie over de functie sorteren
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 10%

---


# sort {#sort}

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
