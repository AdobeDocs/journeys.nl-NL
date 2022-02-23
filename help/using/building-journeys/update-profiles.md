---
product: adobe campaign
title: Profiel bijwerken
description: Profiel bijwerken
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 64f415f3a4120685b64a4b1dc15bf004e86b35d2
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 2%

---

# Profiel bijwerken {#update-profile}

De **[!UICONTROL Update profile]** Met actieactiviteit kunt u een bestaand Adobe Experience Platform-profiel bijwerken met informatie die afkomstig is van de gebeurtenis, een gegevensbron of een specifieke waarde gebruiken.

## Belangrijke opmerkingen

* De **Profiel bijwerken** Actie kan alleen worden gebruikt tijdens reizen die beginnen met een gebeurtenis met een naamruimte.
* Met de handeling worden alleen bestaande velden bijgewerkt. Er worden geen nieuwe profielvelden gemaakt.
* U kunt de **Profiel bijwerken** actie om ervaringsgebeurtenissen te genereren, bijvoorbeeld een aankoop.
* Net als bij andere acties kunt u een alternatief pad definiëren in het geval van een fout of time-out. U kunt geen twee acties parallel plaatsen.
* Het updateverzoek dat naar het Platform wordt verzonden, wordt snel verzonden, maar niet onmiddellijk/binnen een seconde. Het duurt normaal een paar seconden, maar soms nog meer zonder garantie. Als een handeling bijvoorbeeld &#39;field 1&#39; gebruikt die is bijgewerkt met een handeling Profiel bijwerken die eerder is geplaatst, mag u niet verwachten dat &#39;field 1&#39; wordt bijgewerkt in de handeling.
* In de testmodus wordt de profielupdate niet gesimuleerd. De update wordt uitgevoerd op het testprofiel.
* De **Profiel bijwerken** activiteit steunt geen gebieden XDM die als opsomming worden bepaald.

## De profielupdate gebruiken

1. Ontwerp uw reis door met een gebeurtenis te beginnen. Zie dit [sectie](../building-journeys/journey.md).

1. In de **Handeling** van het palet, zet de **Profiel bijwerken** op het canvas.

   ![](../assets/profileupdate0.png)

1. Selecteer een schema in de lijst.

1. Klikken op **Velden** om het veld te selecteren dat u wilt bijwerken. Er kan slechts één veld worden geselecteerd.

   ![](../assets/profileupdate2.png)

1. Selecteer een gegevensset in de lijst.

   >[!NOTE]
   >
   >De **Profiel bijwerken** De actie werkt de profielgegevens in realtime bij, maar werkt datasets niet bij. De datasetselectie is nodig aangezien het profiel een verslag met betrekking tot een dataset is.

1. Klik op de knop **Waarde** veld voor het definiëren van de waarde die u wilt gebruiken:

   * Met de eenvoudige expressieeditor kunt u een veld uit een gegevensbron of uit de binnenkomende gebeurtenis selecteren.

      ![](../assets/profileupdate4.png)

   * Als u een specifieke waarde wilt definiëren of geavanceerde functies wilt gebruiken, klikt u op **Geavanceerde modus**.

      ![](../assets/profileupdate3.png)

De **Profiel bijwerken** is nu geconfigureerd.

![](../assets/profileupdate1.png)
