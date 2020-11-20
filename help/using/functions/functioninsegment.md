---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Meer informatie over de functie in Segment
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 6%

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
