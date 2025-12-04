---
product: adobe campaign
title: matchRegExp
description: Meer informatie over de functie matchRegExp
feature: Journeys
role: Developer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 7%

---

# matchRegExp {#matchRegExp}

Retourneert true als de tekenreeks in de eerste parameter overeenkomt met de reguliere expressie in de tweede parameter. Voor meer informatie, zie [ deze pagina ](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Categorie

String

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
