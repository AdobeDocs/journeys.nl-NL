---
product: adobe campaign
solution: Journey Orchestration
title: listSize
description: Meer informatie over de functie listSize
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '45'
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
