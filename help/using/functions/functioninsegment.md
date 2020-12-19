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

Segmenten worden gedefinieerd in [Adobe Experience Platform](https://platform.adobe.com/segment/overview). De uitdrukkingsredacteur verstrekt een autocompleted lijst van segmenten.

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

De functie zal **[!UICONTROL true]** terugkeren als het individu binnen de reisinstantie deel van het segment van Adobe Experience Platform genoemd &quot;mannen over 50&quot; uitmaakt, anders **[!UICONTROL false]**.
