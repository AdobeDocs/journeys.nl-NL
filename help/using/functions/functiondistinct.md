---
product: adobe campaign
solution: Journey Orchestration
title: distinct
description: Meer informatie over de functie afzonderlijk
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 13%

---


# distinct {#distinct}

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
