---
product: adobe campaign
title: replaceAll
description: Meer informatie over de functie replaceAll
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 9%

---

# replaceAll {#replaceAll}

Vervangt alle instanties die overeenkomen met de doeltekenreeks door de vervangende tekenreeks in de basistekenreeks.

De vervanging vindt plaats vanaf het begin van de tekenreeks tot het einde. Als u bijvoorbeeld &quot;aa&quot; vervangt door &quot;b&quot; in de tekenreeks &quot;aaa&quot;, resulteert dit in &quot;ba&quot; in plaats van &quot;ab&quot;.

## Categorie

Tekenreeks

## Functiesyntaxis

`replaceAll(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|--------------|
| basis | string |
| target | string |
| vervanging | string |

## Handtekening en type geretourneerd

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Retourneert een tekenreeks.

## Voorbeeld

`replaceAll("Hello World", "l", "x")`

Retourneert &quot;Hexxo Worxd&quot;.
