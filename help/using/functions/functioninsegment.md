---
title: inSegment
description: Meer informatie over de functie in Segment
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 1%

---


# inSegment {#inSegment}

Controleert of een individu tot een bepaald segment behoort.

De segmentnaam moet een tekenreeksconstante zijn. Het kan geen veldverwijzing of expressie zijn.

Segmenten worden gedefinieerd in de [Adobe Experience Platform](https://platform.adobe.com/segment/overview). De uitdrukkingsredacteur verstrekt een autocompleted lijst van segmenten.

>[!NOTE]
>
>U kunt tot 100 segmenten terugwinnen.

## Categorie

Adobe Experience Platform

## Functiesyntaxis

`inSegment(<parameter>)`

## Parameters

| Parameter | Beschrijving | Type |
|--- |--- |--- |
| Segment | De segmentnaam | `<string>` |

## Handtekening en type geretourneerd

`inSegment(<string>)`

Retourneert een Booleaanse waarde.

## Voorbeeld

`inSegment("men over 50")`

Uitleg:

De functie wordt geretourneerd **[!UICONTROL true]** als de persoon binnen de reisinstantie deel uitmaakt van het Adobe Experience Platform-segment met de naam &quot;mannen boven 50&quot;, **[!UICONTROL false]** anders.
