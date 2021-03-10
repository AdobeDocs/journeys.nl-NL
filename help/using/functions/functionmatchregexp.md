---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: Meer informatie over de functie matchRegExp
feature: Reizen
role: Gegevensengineer
level: Ervaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 5%

---


# matchRegExp {#matchRegExp}

Retourneert true als de tekenreeks in de eerste parameter overeenkomt met de reguliere expressie in de tweede parameter. Zie [deze pagina](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html) voor meer informatie.

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

Retourneert true.

## Voorbeeld

`matchRegExp("Hello World", "Hello\s+World")`

Retourneert true.

Uitleg:

Hier controleert u of de tekenreeks voldoet aan de reguliere expressie (Java-syntaxis): begint met &quot;Hello&quot;, dan elk type tekenreeks en eindigt met &quot;World&quot;.
