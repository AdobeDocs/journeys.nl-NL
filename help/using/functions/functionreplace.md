---
product: adobe campaign
solution: Journey Orchestration
title: replace
description: Meer informatie over de functie replace
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 6%

---


# replace {#replace}

Vervangt de eerste instantie die overeenkomt met de doeltekenreeks door de vervangende tekenreeks in de basistekenreeks.

De vervanging vindt plaats vanaf het begin van de tekenreeks tot het einde. Als u bijvoorbeeld &quot;aa&quot; vervangt door &quot;b&quot; in de tekenreeks &quot;aaa&quot;, resulteert dit in &quot;ba&quot; in plaats van &quot;ab&quot;.

## Categorie

Tekenreeks

## Functiesyntaxis

`replace(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|--------------|
| basis | string |
| target | string |
| vervanging | string |

## Handtekening en type geretourneerd

`replace(<base>,<target>,<replacement>)`

Retourneer een tekenreeks.

## Voorbeeld

`replace("Hello World", "l", "x")`

Retourneert &quot;Hexlo World&quot;.
