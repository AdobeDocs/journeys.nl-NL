---
product: adobe campaign
title: Aangepaste acties configureren
description: Leer hoe u een aangepaste handeling configureert
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 7ad2419854b4fcecae7fbb20bdd6a6f2fbc04988
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 12%

---

# Aangepaste acties configureren {#concept_sxy_bzs_dgb}

Als u een derdesysteem gebruikt om berichten te verzenden of als u wilt [!DNL Journey Orchestration] om API vraag naar een derdesysteem te verzenden, is dit waar u zijn verbinding vormt om [!DNL Journey Orchestration]. De aangepaste actie die door technische gebruikers is gedefinieerd, is dan beschikbaar in het linkerpalet van uw reis, in het dialoogvenster **[!UICONTROL Action]** categorie (zie [deze pagina](../building-journeys/about-action-activities.md). Hier volgen enkele voorbeelden van systemen waarmee u verbinding kunt maken met aangepaste handelingen: Epsilon, Facebook, Adobe.io, Firebase, enz.

Beperkingen worden vermeld in [deze pagina](../about/limitations.md).

In parameters voor aangepaste handelingen kunt u een eenvoudige verzameling en een verzameling objecten doorgeven. Wat de beperkingen betreft, kunt u verwijzen naar [deze pagina](../usecase/collections.md#limitations). Let ook op dat de parameters een verwacht formaat hebben (voorbeeld: tekenreeks, decimaal, enz.). U moet deze verwachte formaten zorgvuldig respecteren. Zie dit [use case](../usecase/collections.md).

Hier zijn de belangrijkste stappen die worden vereist om een douaneactie te vormen:

1. Van de **[!UICONTROL Actions]** lijst, klikt u op **[!UICONTROL Add]** om een nieuwe handeling te maken. Het deelvenster Handelingsconfiguratie wordt aan de rechterkant van het scherm geopend.

   ![](../assets/custom2.png)

1. Voer een naam in voor de handeling.

   >[!NOTE]
   >
   >Gebruik geen spaties of speciale tekens. Gebruik niet meer dan 30 tekens.

1. Voeg een beschrijving aan uw actie toe. Deze stap is optioneel.
1. Het aantal ritten dat deze handeling gebruikt, wordt weergegeven in het dialoogvenster **[!UICONTROL Used in]** veld. U kunt op de knop **[!UICONTROL View journeys]** om de lijst met reizen weer te geven die deze handeling gebruiken.
1. Verschillende definiëren **[!UICONTROL URL Configuration]** parameters. Zie [deze pagina](../action/url-configuration.md).
1. Configureer de **[!UICONTROL Authentication]** sectie. Deze configuratie is het zelfde als voor gegevensbronnen.  Zie [deze sectie](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definieer de **[!UICONTROL Action parameters]**. Zie [deze pagina](../action/defining-the-message-parameters.md).
1. Klik op **[!UICONTROL Save]**.

   De aangepaste handeling is nu geconfigureerd en klaar om te worden gebruikt tijdens uw reizen. Zie [deze pagina](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Wanneer een douaneactie in een reis wordt gebruikt, zijn de meeste parameters read-only. U kunt de **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** en de **[!UICONTROL Authentication]** sectie.
