---
product: adobe campaign
title: distinct
description: Meer informatie over de functie afzonderlijk
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 15%

---

# onderscheiden {#distinct}

Retourneert de verschillende waarden van de lijst zonder null-waarden.

## Categorie

Lijst

## Functiesyntaxis

`distinct(<parameter>)`

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

## Handtekeningen en geretourneerde typen

`distinct(<listInteger>)`

Retourneert een lijst met gehele getallen.

`distinct(<listDecimal>)`

Retourneert een lijst met decimalen.

`distinct(<listString>)`

Retourneert een lijst met tekenreeksen.

`distinct(<listDateTimeOnly>)`

Keert een lijst van datetimes zonder tijdzone terug te overwegen.

`distinct(<listDateTime>)`

Retourneert een lijst met datetimes.

`distinct(<listBoolean>)`

Retourneert een lijst met laarzen.

`distinct(<listDuration>)`

Retourneert een lijst met tijdsduur.

## Voorbeelden

`distinct([10,2,10,null])`

Retourneert `[10, 2]`.
