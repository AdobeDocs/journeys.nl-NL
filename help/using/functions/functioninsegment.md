---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Meer informatie over de functie in Segment
feature: Reizen
role: Gegevensengineer
level: Ervaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 7%

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
