---
product: adobe campaign
solution: Journey Orchestration
title: Een segment gebruiken
description: Leer hoe u een segment gebruikt
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 2%

---


# Segmenten gebruiken in voorwaarden {#using-a-segment}

Deze sectie verklaart hoe te om een segment in een reisvoorwaarde te gebruiken. Om te leren hoe te om een **[!UICONTROL Segment qualification]** gebeurtenis in uw reis te gebruiken, verwijs naar dit [sectie](../building-journeys/segment-qualification-events.md).

Voer de volgende stappen uit om een segment te gebruiken in een reisvoorwaarde:

1. Open een reis, laat vallen een **[!UICONTROL Condition]** activiteit en kies **Voorwaarde van de Gegevensbron**.
   ![](../assets/journey47.png)

1. Klik **[!UICONTROL Add a path]** voor elk extra nodig pad. Klik voor elk pad op het veld **[!UICONTROL Expression]**.

   ![](../assets/segment3.png)

1. Ontvouw **[!UICONTROL Segments]** knoop aan de linkerkant. Sleep het segment dat u voor de voorwaarde wilt gebruiken en zet het neer. De standaardwaarde voor het segment is true.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Alleen personen met de **Realized** en **Existing**-segmentparticipatiestatus worden beschouwd als leden van het segment. Raadpleeg de [documentatie voor segmentatieservice](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results) voor meer informatie over het evalueren van een segment.

Voor meer informatie over reisvoorwaarden en hoe te om de eenvoudige uitdrukkingsredacteur te gebruiken, verwijs naar [Condition activity](../building-journeys/condition-activity.md#about_condition).