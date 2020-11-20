---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: Meer informatie over de functie containWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 8%

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
