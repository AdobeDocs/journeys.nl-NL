---
product: adobe campaign
title: inSegment
description: Meer informatie over de functie in Segment
feature: Journeys
role: Developer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 4%

---

# inSegment {#inSegment}

Controleert of een individu tot een bepaald segment behoort.

>[!NOTE]
>
>U kunt tot 100 segmenten terugwinnen.

De segmentnaam moet een constante tekenreeks zijn. Het kan geen veldverwijzing of expressie zijn.

De segmenten worden bepaald in [&#x200B; Adobe Experience Platform &#x200B;](https://platform.adobe.com/segment/overview). De uitdrukkingsredacteur verstrekt een autocompleted lijst van segmenten.

Segmenten kunnen drie statussen hebben:

* bestaande: entiteit blijft deel uitmaken van het segment.
* gerealiseerd: entiteit betreedt het segment.
* verlaten: entiteit verlaat het segment.

Slechts zullen de individuen met de **Geleide** en **Bestaande** status van de segmentparticipatie als leden van het segment worden beschouwd. Voor meer op hoe te om een segment te evalueren, verwijs naar de [&#x200B; documentatie van de Dienst van de Segmentatie &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=nl-NL#interpret-segment-results).

`IF inSegment('segmentName') == true` betekent dat u een segmentLidmaatschap met de ingegaan/bestaande status hebt.

`ELSE inSegment('segmentName') == false` betekent dat u een segmentLidmaatschap van de verlaten status hebt.

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

De functie retourneert **[!UICONTROL true]** als de persoon binnen de reisinstantie deel uitmaakt van het Adobe Experience Platform-segment met de naam &quot;men boven 50&quot;, anders **[!UICONTROL false]** .
