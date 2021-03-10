---
product: adobe campaign
solution: Journey Orchestration
title: Informatie over het configureren van aangepaste acties
description: Leer hoe u een aangepaste handeling configureert
feature: Reizen
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 15%

---


# Informatie over het configureren van aangepaste acties {#concept_sxy_bzs_dgb}

Als u een derdesysteem gebruikt om berichten te verzenden of als u [!DNL Journey Orchestration] API vraag naar een derdesysteem wilt verzenden, is dit waar u zijn verbinding aan [!DNL Journey Orchestration] vormt. De aangepaste actie die door technische gebruikers is gedefinieerd, is dan beschikbaar in het linkerpalet van uw reis, in de categorie **[!UICONTROL Action]** (zie [deze pagina](../building-journeys/about-action-activities.md). Hier volgen enkele voorbeelden van systemen waarmee u verbinding kunt maken met aangepaste handelingen: Epsilon, Facebook, Adobe.io, Firebase, enz.
Beperkingen worden vermeld in [deze pagina](../about/limitations.md).

Hier zijn de belangrijkste stappen die worden vereist om een douaneactie te vormen:

1. Klik in de lijst **[!UICONTROL Actions]** op **[!UICONTROL Add]** om een nieuwe handeling te maken. Het deelvenster Handelingsconfiguratie wordt aan de rechterkant van het scherm geopend.

   ![](../assets/custom2.png)

1. Voer een naam in voor de handeling.

   >[!NOTE]
   >
   >Gebruik geen spaties of speciale tekens. Gebruik niet meer dan 30 tekens.

1. Voeg een beschrijving aan uw actie toe. Deze stap is optioneel.
1. Het aantal ritten dat deze handeling gebruikt, wordt weergegeven in het veld **[!UICONTROL Used in]**. U kunt op de knop **[!UICONTROL View journeys]** klikken om de lijst met ritten weer te geven die deze handeling gebruiken.
1. Definieer de verschillende **[!UICONTROL URL Configuration]** parameters. Zie [deze pagina](../action/url-configuration.md).
1. Configureer de sectie **[!UICONTROL Authentication]**. Deze configuratie is het zelfde als voor gegevensbronnen.  Zie [deze sectie](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definieer de **[!UICONTROL Message parameters]**. Zie [deze pagina](../action/defining-the-message-parameters.md).
1. Klik op **[!UICONTROL Save]**.

   De aangepaste handeling is nu geconfigureerd en klaar om te worden gebruikt tijdens uw reizen. Zie [deze pagina](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Wanneer een douaneactie in een reis wordt gebruikt, zijn de meeste parameters read-only. U kunt alleen de velden **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** en **[!UICONTROL Authentication]** wijzigen.
