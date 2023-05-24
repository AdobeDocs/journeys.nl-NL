---
product: adobe campaign
title: distinctCountWithNull
description: Meer informatie over de functie differentCountWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 30%

---

# distinctCountWithNull {#distinctCountWithNull}

Telt het aantal verschillende waarden inclusief de null-waarden.

## Categorie

Samenvoeging

## Functiesyntaxis

`distinctCountWithNull(<listAny>)`

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
| Lijst | listDateOnly |

## Handtekening en type geretourneerd

`distinctCountWithNull(<listAny>)`

Retourneert een geheel getal.

## Voorbeeld

`distinctCountWithNull([10,2,10,null])`

Retourneert 3.
