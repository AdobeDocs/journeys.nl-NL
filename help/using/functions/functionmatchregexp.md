---
product: adobe campaign
title: matchRegExp
description: Meer informatie over de functie matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 6%

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
