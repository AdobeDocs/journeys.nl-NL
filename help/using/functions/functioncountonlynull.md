---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: Meer informatie over de functie countOnlyNull
feature: Reizen
role: Gegevensengineer
level: Ervaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 24%

---


# countOnlyNull {#countOnlyNull}

Telt het aantal null-waarden in de lijst.

## Categorie

Samenvoeging

## Functiesyntaxis

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

Retourneert een geheel getal.

## Voorbeeld

`count([10,2,10,null])`

Retourneert 1.
