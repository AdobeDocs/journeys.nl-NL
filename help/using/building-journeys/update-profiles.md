---
product: adobe campaign
title: Profiel bijwerken
description: Profiel bijwerken
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# Profiel bijwerken {#update-profile}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Met de **[!UICONTROL Update profile]** -actieactiviteit kunt u een bestaand Adobe Experience Platform-profiel bijwerken met informatie die afkomstig is van de gebeurtenis, een gegevensbron of het gebruik van een specifieke waarde.

## Belangrijke opmerkingen

* De **het profiel van de Update** actie kan slechts in reizen worden gebruikt die met een gebeurtenis beginnen die een namespace heeft.
* Met de handeling worden alleen bestaande velden bijgewerkt. Er worden geen nieuwe profielvelden gemaakt.
* U kunt niet de **het profiel van de Update** actie gebruiken om ervaringsgebeurtenissen, bijvoorbeeld een aankoop te produceren.
* Net als bij andere acties kunt u een alternatief pad definiëren in het geval van een fout of time-out. U kunt geen twee acties parallel plaatsen.
* Het updateverzoek dat naar Platform wordt verzonden zal snel maar niet onmiddellijk/binnen een seconde zijn. Het duurt normaal een paar seconden, maar soms nog meer zonder garantie. Als een handeling bijvoorbeeld &#39;field 1&#39; gebruikt die is bijgewerkt met een handeling Profiel bijwerken die eerder is geplaatst, mag u niet verwachten dat &#39;field 1&#39; wordt bijgewerkt in de handeling.
* In de testmodus wordt het profiel niet bijgewerkt. De update wordt uitgevoerd op het testprofiel.
* De **het profiel van de Update** activiteit steunt geen gebieden XDM die als opsomming worden bepaald.

## De profielupdate gebruiken

1. Ontwerp uw reis door met een gebeurtenis te beginnen. Zie deze [&#x200B; sectie &#x200B;](../building-journeys/journey.md).

1. In de **sectie van de Actie** van het palet, laat vallen de **het profiel van de Update** activiteit in het canvas.

   ![](../assets/profileupdate0.png)

1. Selecteer een schema in de lijst.

1. Klik op **Gebieden** om het gebied te selecteren u wilt bijwerken. Er kan slechts één veld worden geselecteerd.

   ![](../assets/profileupdate2.png)

1. Selecteer een gegevensset in de lijst.

   >[!NOTE]
   >
   >De **het profiel van de Update** actie werkt de profielgegevens in real time bij, maar het werkt geen datasets bij. De datasetselectie is nodig aangezien het profiel een verslag met betrekking tot een dataset is.

1. Klik op het **gebied van de Waarde** om de waarde te bepalen u wilt gebruiken:

   * Met de eenvoudige expressieeditor kunt u een veld uit een gegevensbron of uit de binnenkomende gebeurtenis selecteren.

     ![](../assets/profileupdate4.png)

   * Als u een specifieke waarde of hefboomwerking geavanceerde functies wilt bepalen, klik op **Geavanceerde wijze**.

     ![](../assets/profileupdate3.png)

Het **profiel van de Update** wordt nu gevormd.

![](../assets/profileupdate1.png)
