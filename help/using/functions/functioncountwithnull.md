---
product: adobe campaign
title: countWithNull
description: Meer informatie over de functie countWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 31%

---

# countWithNull {#countWithNull}

Telt alle elementen van de lijst met inbegrip van ongeldige waarden.

## Categorie

Samenvoeging

## Functiesyntaxis

`countWithNull(<listAny>)`

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

`countWithNull(<listAny>)`

Retourneert een geheel getal.

## Voorbeeld

`count([10,2,10,null])`

Retourneert 4.
