---
product: adobe campaign
title: split
description: Meer informatie over de functie splitsen
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 9%

---

# splitsen {#split}

Splitst de eerste argumenttekenreeks op met een scheidingstekenreeks (tweede argumenttekenreeks, die een reguliere expressie kan zijn) om een lijst met tekenreeksen (tokens) te maken.

## Categorie

Tekenreeks

## Functiesyntaxis

`split(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| invoertekenreeks | string |
| scheidingstekenreeks | string |

## Handtekeningen en type geretourneerd

`split(<input string>, <separator string>)`

Retourneert een listString.

## Voorbeeld

`split(["A_B_C"], "_")`

Retourneert `["A","B","C"]`

Voorbeeld met een gebeurtenisveld &#39;event.appVersion&#39; met waarde: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Retourneert `["20", "45", "2", "3434"]`
