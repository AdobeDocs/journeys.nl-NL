---
title: matchRegExp
description: Meer informatie over de functie matchRegExp
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
source-wordcount: '85'
ht-degree: 4%

---


# matchRegExp {#matchRegExp}

Retourneert true als de tekenreeks in de eerste parameter overeenkomt met de reguliere expressie in de tweede parameter. Zie [deze pagina](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)voor meer informatie.

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
