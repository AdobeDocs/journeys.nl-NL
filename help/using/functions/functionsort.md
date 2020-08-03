---
title: sorteren
description: Meer informatie over de functie sorteren
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

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
