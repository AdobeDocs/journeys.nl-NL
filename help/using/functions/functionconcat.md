---
product: adobe campaign
solution: Journey Orchestration
title: concat
description: Meer informatie over het functieconcept
feature: Reizen
role: Gegevensengineer
level: Ervaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 13%

---


# concat {#concat}

Voegt twee tekenreeksparameters of een lijst met tekenreeksen samen.

## Categorie

Tekenreeks

## Functiesyntaxis

`concat(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| Lijst | listString |
| string | string |

## Handtekening en type geretourneerd

`concat(<string>,<string>)`

`concat(<listString>)`

Retourneert een tekenreeks.

## Voorbeeld

`concat("Hello","World")`

Retourneert &quot;HelloWorld&quot;.

`concat(["Hello"," ","World"])`

Retourneert &quot;Hello World&quot;.
