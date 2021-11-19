---
product: adobe campaign
title: matchRegExp
description: Meer informatie over de functie matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 11%

---

# matchRegExp {#matchRegExp}

Retourneert true als de tekenreeks in de eerste parameter overeenkomt met de reguliere expressie in de tweede parameter. Zie voor meer informatie [deze pagina](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Categorie

Tekenreeks

## Functiesyntaxis

`matchRegExp(<parameters>)`

## Parameters

| Parameter | Type |
|--- |--- |
| string | string |
| regexp | string |

## Handtekening en type geretourneerd

`matchRegExp(<string>,<string>)`

Retourneert een Booleaanse waarde.

## Voorbeeld

`matchRegExp("username@adobe.com", "*adobe")`

Retourneert true.
