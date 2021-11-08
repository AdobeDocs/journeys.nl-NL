---
product: adobe campaign
title: countOnlyNull
description: Meer informatie over de functie countOnlyNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 31%

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
| Lijst | listDateOnly |

## Handtekening en type geretourneerd

`countOnlyNull(<listAny>)`

Retourneert een geheel getal.

## Voorbeeld

`countOnlyNull([10,2,10,null])`

Retourneert 1.
