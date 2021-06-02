---
product: adobe campaign
title: Van de ene journey naar de andere gaan
description: Van de ene journey naar de andere gaan
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 4%

---

# Profiel bijwerken {#update-profile}

Met de actieactiviteit **[!UICONTROL Update profile]** kunt u een bestaand Adobe Experience Platform-profiel bijwerken met informatie die afkomstig is van de gebeurtenis, een gegevensbron of het gebruik van een specifieke waarde.

## Belangrijke opmerkingen

* De handeling **Update profile** kan alleen worden gebruikt tijdens reizen die beginnen met een gebeurtenis met een naamruimte.
* Met de handeling worden alleen bestaande velden bijgewerkt. Er worden geen nieuwe profielvelden gemaakt.
* U kunt de handeling **Update profile** niet gebruiken om ervaringsgebeurtenissen te genereren, bijvoorbeeld een aankoop.
* Net als bij andere acties kunt u een alternatief pad definiëren in het geval van een fout of time-out. U kunt geen twee acties parallel plaatsen.
* Het updateverzoek dat naar het Platform wordt verzonden, wordt snel verzonden, maar niet onmiddellijk/binnen een seconde. Het duurt normaal een paar seconden, maar soms nog meer zonder garantie. Als een handeling bijvoorbeeld &#39;field 1&#39; gebruikt die is bijgewerkt met een handeling Profiel bijwerken die eerder is geplaatst, mag u niet verwachten dat &#39;field 1&#39; wordt bijgewerkt in de handeling.
* Gegevensbronnen hebben een begrip van cacheduur, op het niveau van de gebiedsgroep. Als u tijdens een rit een profielveld wilt gebruiken dat onlangs is bijgewerkt, moet u zorgvuldig een zeer korte cache-duur definiëren.
* In de testmodus wordt de profielupdate niet gesimuleerd. De update wordt uitgevoerd op het testprofiel.

## De profielupdate gebruiken

1. Ontwerp uw reis door met een gebeurtenis te beginnen. Zie deze [sectie](../building-journeys/journey.md).

1. Plaats in de sectie **Actie** van het palet de **Actie bijwerken** op het canvas.

   ![](../assets/profileupdate0.png)

1. Selecteer een schema in de lijst.

1. Klik op **Fields** om het gebied te selecteren u wilt bijwerken. Er kan slechts één veld worden geselecteerd.

   ![](../assets/profileupdate2.png)

1. Selecteer een gegevensset in de lijst. De selectie van de dataset zal bepalen waar de nieuwe waarde van het profielgebied zal worden opgeslagen.

1. Klik op het veld **Waarde** om de waarde te definiëren die u wilt gebruiken:

   * Met de eenvoudige expressieeditor kunt u een veld uit een gegevensbron of uit de binnenkomende gebeurtenis selecteren.

      ![](../assets/profileupdate4.png)

   * Als u een specifieke waarde wilt definiëren of geavanceerde functies wilt gebruiken, klikt u op **Geavanceerde modus**.

      ![](../assets/profileupdate3.png)

Het **Update profiel** wordt nu gevormd.

![](../assets/profileupdate1.png)
