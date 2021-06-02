---
product: adobe campaign
title: distinctCount
description: Meer informatie over de functie differentCount
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 27%

---

# differentCount{#distinctCount}

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
