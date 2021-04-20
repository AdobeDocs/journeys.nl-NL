---
product: adobe campaign
solution: Journey Orchestration
title: count
description: Meer informatie over het aantal functies
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 22%

---


# count {#count}

Telt de elementen van de lijst die geen rekening houden met de ongeldige waarden.

## Categorie

Samenvoeging

## Functiesyntaxis

`count(<listAny>)`

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

`count(<listAny>)`

Retourneert een geheel getal.

## Voorbeeld

`count([10,2,10,null])`

Retourneert 3.
