---
product: adobe campaign
title: distinctWithNull
description: Meer informatie over de functie clearWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 13%

---

# differentWithNull {#distinctWithNull}

Retourneert de verschillende waarden van de lijst. Als de lijst minstens één ongeldige waarde heeft, zal een ongeldige waarde in de teruggekeerde lijst zijn.

## Categorie

Lijst

## Functiesyntaxis

`distinctWithNull(<parameter>)`

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

`distinctWithNull(<listInteger>)`

Retourneert een lijst met gehele getallen.

`distinctWithNull(<listDecimal>)`

Retourneert een lijst met decimalen.

`distinctWithNull(<listString>)`

Retourneert een lijst met tekenreeksen.

`distinctWithNull(<listDateTimeOnly>)`

Keert een lijst van datetimes zonder tijdzone terug te overwegen.

`distinctWithNull(<listDateTime>)`

Retourneert een lijst met datetimes.

`distinctWithNull(<listBoolean>)`

Retourneert een lijst met laarzen.

`distinctWithNull(<listDuration>)`

Retourneert een lijst met tijdsduur.

## Voorbeelden

`distinctWithNull([10,2,10,null])`

Retourneert [10, 2, null]
