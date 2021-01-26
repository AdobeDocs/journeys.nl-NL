---
product: adobe campaign
solution: Journey Orchestration
title: splitsen
description: Meer informatie over de functie splitsen
translation-type: tm+mt
source-git-commit: 135485c097f99483c2ddb3d03e0552f9ac134b44
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 4%

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
