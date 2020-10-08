---
title: replace
description: Meer informatie over de functie replace
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 5%

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
