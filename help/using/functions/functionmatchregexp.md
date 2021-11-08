---
product: adobe campaign
title: matchRegExp
description: Meer informatie over de functie matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 8%

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

`matchRegExp("Hello World", "Hello\s+World")`

Retourneert true.

Uitleg:

Hier controleert u of de tekenreeks voldoet aan de reguliere expressie (Java-syntaxis): begint met &quot;Hello&quot;, dan elk type tekenreeks en eindigt met &quot;World&quot;.
