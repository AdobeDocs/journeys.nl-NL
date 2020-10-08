---
title: Informatie over het configureren van aangepaste acties
description: Leer hoe u een aangepaste handeling configureert
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 12%

---


# Informatie over het configureren van aangepaste acties {#concept_sxy_bzs_dgb}

Als u een derdesysteem gebruikt om berichten te verzenden of als u API vraag [!DNL Journey Orchestration] naar een derdesysteem wilt verzenden, is dit waar u zijn verbinding vormt aan [!DNL Journey Orchestration]. De aangepaste actie die door technische gebruikers is gedefinieerd, is dan beschikbaar in het linkerpalet van uw reis, in de **[!UICONTROL Action]** categorie (zie [](../building-journeys/about-action-activities.md). Hier volgen enkele voorbeelden van systemen waarmee u verbinding kunt maken met aangepaste handelingen: Epsilon, Facebook, Adobe.io, Firebase, enz.
Hier worden beperkingen weergegeven: [](../action/custom-action-limitations.md).

Hier zijn de belangrijkste stappen die worden vereist om een douaneactie te vormen:

1. Klik in de **[!UICONTROL Actions]** lijst **[!UICONTROL Add]** om een nieuwe handeling te maken. Het deelvenster Handelingsconfiguratie wordt aan de rechterkant van het scherm geopend.

   ![](../assets/custom2.png)

1. Voer een naam in voor de handeling.

   >[!NOTE]
   >
   >Gebruik geen spaties of speciale tekens. Gebruik niet meer dan 30 tekens.

1. Voeg een beschrijving aan uw actie toe. Deze stap is optioneel.
1. The number of journeys that use this action is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. Define the different **[!UICONTROL URL Configuration]** parameters. Zie [](../action/url-configuration.md).
1. Configureer de **[!UICONTROL Authentication]** sectie. Deze configuratie is het zelfde als voor gegevensbronnen.  Zie [](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Define the **[!UICONTROL Message parameters]**. Zie [](../action/defining-the-message-parameters.md).
1. Klik op **[!UICONTROL Save]**.

   De aangepaste handeling is nu geconfigureerd en klaar om te worden gebruikt tijdens uw reizen. Zie [](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Wanneer een douaneactie in een reis wordt gebruikt, zijn de meeste parameters read-only. U kunt alleen de **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** velden en de **[!UICONTROL Authentication]** sectie wijzigen.
