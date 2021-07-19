---
product: adobe campaign
title: listSize
description: Meer informatie over de functie listSize
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: c0d34a8d-33e9-4c7b-9b7d-a1b21ed96d35
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%

---

# listSize {#listSize}

Telt het aantal elementen in de lijst.

## Categorie

Lijst

## Functiesyntaxis

`listSize(<parameters>)`

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

## Handtekeningen en type geretourneerd

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

Retourneer een geheel getal.

## Voorbeeld

`listSize([10,2,3])`

Retourneert 3.
