---
product: adobe campaign
title: notEqualIgnoreCase
description: Meer informatie over de functie notEqualIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 10%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

Controleer of de eerste argumenttekenreeks met de tweede argumenttekenreeks anders is, waarbij rekening wordt gehouden met hoofdletters en kleine letters.

## Categorie

Tekenreeks

## Functiesyntaxis

`notEqualIgnoreCase(<parameters>)`

## Parameters

* string

## Handtekening en type geretourneerd

`notEqualIgnoreCase(<string>,<string>)`

Retourneert een Booleaanse waarde.

## Voorbeeld

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
