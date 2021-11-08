---
product: adobe campaign
title: getListItem
description: Meer informatie over de functie gstListItem
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 16%

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
| list | listDateOnly |
| index | integer |

## Handtekeningen en type geretourneerd

`getListItem(<listInteger>,<index>)`

Retourneert een geheel getal.

`getListItem(<listDecimal>,<index>)`

Retourneert een decimaal.

`getListItem(<listString>,<index>)`

Retourneert een tekenreeks.

`getListItem(<listDateTimeOnly>,<index>)`

Retourneert een datetime zonder rekening te houden met tijdzone.

`getListItem(<listDateTime>,<index>)`

Retourneert een datetime.

`getListItem(<listDateOnly>,<index>)`

Retourneert een lijst met datums.

`getListItem(<listBoolean>,<index>)`

Retourneert een Booleaanse waarde.

`getListItem(<listDuration>,<index>)`

Retourneert een duur.

## Voorbeeld

`getListItem([10, 2, 3], 1)`

Retourneert &quot;2&quot;

`getListItem(["A", "B", "C"], 2)`
Retourneert &quot;C&quot;

Voorbeelden met een gebeurtenisveld &#39;event.appVersion&#39; met waarde: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Retourneert `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Retourneert &quot;20&quot;
