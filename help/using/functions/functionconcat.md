---
title: concat
description: Meer informatie over het functieconcept
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
source-wordcount: '40'
ht-degree: 12%

---


# concat {#concat}

Voegt twee tekenreeksparameters of een lijst met tekenreeksen samen.

## Categorie

Tekenreeks

## Functiesyntaxis

`concat(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| Lijst | listString |
| string | string |

## Handtekening en type geretourneerd

`concat(<string>,<string>)`

`concat(<listString>)`

Retourneert een tekenreeks.

## Voorbeeld

`concat("Hello","World")`

Retourneert &quot;HelloWorld&quot;.

`concat(["Hello"," ","World"])`

Retourneert &quot;Hello World&quot;.
