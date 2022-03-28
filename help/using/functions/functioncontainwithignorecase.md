---
product: adobe campaign
title: containIgnoreCase
description: Meer informatie over de functie containIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 14%

---

# containIgnoreCase {#containIgnoreCase}

Controleert of de tweede argumenttekenreeks zich in de eerste argumenttekenreeks bevindt, zonder rekening te houden met de case.

## Categorie

Tekenreeks

## Functiesyntaxis

`containIgnoreCase(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| string | string |
| doorzocht tekenreeks | string |

## Handtekening en type geretourneerd

`containIgnoreCase(<string>,<string>)`

Retourneert een Booleaanse waarde.

## Voorbeeld

`containIgnoreCase("rowing is great", "GREAT")`

Retourneert true.
