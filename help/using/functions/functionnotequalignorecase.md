---
product: adobe campaign
title: notEqualWithIgnoreCase
description: Meer informatie over de functie notEqualWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 18%

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
