---
product: adobe campaign
solution: Journey Orchestration
title: listSize
description: Meer informatie over de functie listSize
feature: Reizen
role: Gegevensengineer
level: Ervaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 24%

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
