---
product: adobe campaign
title: inSegment
description: Meer informatie over de functie in Segment
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 8%

---

# inSegment {#inSegment}

Controleert of een individu tot een bepaald segment behoort.

>[!NOTE]
>
>U kunt tot 100 segmenten terugwinnen.

De segmentnaam moet een tekenreeksconstante zijn. Het kan geen veldverwijzing of expressie zijn.

Segmenten worden gedefinieerd in [Adobe Experience Platform](https://platform.adobe.com/segment/overview). De uitdrukkingsredacteur verstrekt een autocompleted lijst van segmenten.

>[!NOTE]
>
>Alleen personen met de **Realized** en **Existing**-segmentparticipatiestatus worden beschouwd als leden van het segment. Raadpleeg de [documentatie voor segmentatieservice](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results) voor meer informatie over het evalueren van een segment.

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
