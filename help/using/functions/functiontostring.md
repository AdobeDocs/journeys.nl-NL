---
product: adobe campaign
title: toString
description: Meer informatie over de functie toString
feature: Journeys
role: Developer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 3%

---

# toString {#toString}

Zet een argumentwaarde in een koordwaarde om, afhankelijk van zijn type. Voor meer informatie over gegevenstypes, verwijs naar [&#x200B; deze pagina &#x200B;](../expression/data-types.md).

## Categorie

Conversie

## Functiesyntaxis

`toString(<parameter>)`

## Parameters

| Parameter | Beschrijving |
|--- |--- |
| dateTime | converteert de datum in UTC-datumnotatie |
| dateTimeOnly | converteert de datum in UTC-datumnotatie |
| duur | converteren naar het overeenkomstige aantal milliseconden als een tekenreeks |
| integer | converteert naar tekenreeksrepresentatie van de waarde (1 wordt &quot;1&quot;) |
| decimaal | converteert naar tekenreeksrepresentatie van de waarde (1,5 wordt &quot;1,5&quot;) |
| boolean | Zet de booleaanse waarde om als &#39;true&#39; (waar), &#39;false&#39; (onwaar) |

## Handtekeningen en type geretourneerd

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Retourneer een tekenreeks.

## Voorbeeld

`toString(4)`

Retourneert &quot;4&quot;.
