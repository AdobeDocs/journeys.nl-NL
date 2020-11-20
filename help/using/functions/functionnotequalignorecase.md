---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Meer informatie over de functie notEqualWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 10%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Controleer of de eerste argumenttekenreeks met de tweede argumenttekenreeks anders is, waarbij rekening wordt gehouden met hoofdletters en kleine letters.

## Categorie

Tekenreeks

## Functiesyntaxis

`notEqualWithIgnoreCase(<parameters>)`

## Parameters

* string

## Handtekening en type geretourneerd

`notEqualWithIgnoreCase(<string>,<string>)`

Retourneert een Booleaanse waarde.

## Voorbeeld

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
