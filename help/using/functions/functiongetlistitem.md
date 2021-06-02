---
product: adobe campaign
title: getListItem
description: Meer informatie over de functie gstListItem
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 6%

---

# getListItem {#gestListItem}

Retourneert het item van de lijst bij de opgegeven index.

## Categorie

Lijst

## Functiesyntaxis

`getListItem(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| index | integer |

## Handtekeningen en type geretourneerd

`getListItem(<listInteger>,<index>)`

Retourneert een lijst met gehele getallen.

`getListItem(<listDecimal>,<index>)`

Retourneert een lijst met decimalen.

`getListItem(<listString>,<index>)`

Retourneert een lijst met tekenreeksen.

`getListItem(<listDateTimeOnly>,<index>)`

Keert een lijst van datetimes zonder tijdzone terug te overwegen.

`getListItem(<listDateTime>,<index>)`

Retourneert een lijst met datetimes.

`getListItem(<listBoolean>,<index>)`

Retourneert een lijst met laarzen.

`getListItem(<listDuration>,<index>)`

Retourneert een lijst met tijdsduur.

## Voorbeeld

`getListItem([10, 2, 3], 1)`

Retourneert &quot;2&quot;

`getListItem(["A", "B", "C"], 3)`
Retourneert &quot;C&quot;

Voorbeelden met een gebeurtenisveld &#39;event.appVersion&#39; met waarde: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Retourneert `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Retourneert &quot;20&quot;
