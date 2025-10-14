---
product: adobe campaign
title: Segmenten gebruiken in voorwaarden
description: Leer hoe u een segment gebruikt
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 4%

---

# Segmenten gebruiken in voorwaarden {#using-a-segment}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Deze sectie verklaart hoe te om een segment in een reisvoorwaarde te gebruiken. Leren hoe te om a **[!UICONTROL Segment qualification]** gebeurtenis in uw reis te gebruiken, verwijs naar dit [&#x200B; sectie &#x200B;](../building-journeys/segment-qualification-events.md).

Voer de volgende stappen uit om een segment te gebruiken in een reisvoorwaarde:

1. Open een reis, laat vallen a **[!UICONTROL Condition]** activiteit en kies de **Voorwaarde van Gegevens Source**.
   ![](../assets/journey47.png)

1. Klik op **[!UICONTROL Add a path]** voor elk extra pad dat nodig is. Klik voor elk pad op het veld **[!UICONTROL Expression]** .

   ![](../assets/segment3.png)

1. Ontgrendel **[!UICONTROL Segments]** node aan de linkerkant. Sleep het segment dat u voor de voorwaarde wilt gebruiken en zet het neer. De standaardwaarde voor het segment is true.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Slechts zullen de individuen met de **Geleide** en **Bestaande** status van de segmentparticipatie als leden van het segment worden beschouwd. Voor meer op hoe te om een segment te evalueren, verwijs naar de [&#x200B; documentatie van de Dienst van de Segmentatie &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=nl-NL#interpret-segment-results).

Voor meer informatie over reisvoorwaarden en hoe te om de eenvoudige uitdrukkingsredacteur te gebruiken, verwijs naar [&#x200B; activiteit van de Voorwaarde &#x200B;](../building-journeys/condition-activity.md#about_condition).
