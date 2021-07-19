---
product: adobe campaign
title: containWithIgnoreCase
description: Meer informatie over de functie containWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 16%

---

# containWithIgnoreCase {#containWithIgnoreCase}

Controleert of de tweede argumenttekenreeks zich in de eerste argumenttekenreeks bevindt, zonder rekening te houden met de case.

## Categorie

Tekenreeks

## Functiesyntaxis

`containWithIgnoreCase(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| string | string |
| doorzocht tekenreeks | string |

## Handtekening en type geretourneerd

`containWithIgnoreCase(<string>,<string>)`

Retourneert een Booleaanse waarde.

## Voorbeeld

`containWithIgnoreCase("rowing is great', "GREAT")`

Retourneert true.
