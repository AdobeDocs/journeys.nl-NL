---
product: adobe campaign
solution: Journey Orchestration
title: distinctCount
description: Meer informatie over de functie differentCount
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 23%

---


# distinctCount{#distinctCount}

Telt het aantal verschillende waarden waarbij de null-waarden worden genegeerd.

## Categorie

Samenvoeging

## Functiesyntaxis

`distinctCount(<listAny>)`

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

## Handtekening en type geretourneerd

`distinctCount(<listAny>)`

Retourneert een geheel getal.

## Voorbeeld

`distinctCount([10,2,10,null])`

Retourneert 2.
