---
product: adobe campaign
title: Aangepaste acties configureren
description: Leer hoe u een aangepaste handeling configureert
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 11%

---

# Aangepaste acties configureren {#concept_sxy_bzs_dgb}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Als u een systeem van derden gebruikt om berichten te verzenden of als u wilt dat [!DNL Journey Orchestration] API-aanroepen verzendt naar een systeem van derden, configureert u de verbinding met [!DNL Journey Orchestration] op deze locatie. De douaneactie die door technische gebruikers wordt bepaald zal dan in het linkerpalet van uw reis, in de **[!UICONTROL Action]** categorie (zie [ deze pagina ](../building-journeys/about-action-activities.md) beschikbaar zijn. Hier zijn een paar voorbeelden van systemen waarmee u verbinding kunt maken met aangepaste acties: Epsilon, Facebook, Adobe.io, Firebase, enzovoort.

De beperkingen worden vermeld in [ deze pagina ](../about/limitations.md).

In parameters voor aangepaste handelingen kunt u een eenvoudige verzameling en een verzameling objecten doorgeven. Met betrekking tot de beperkingen, gelieve te verwijzen naar [ deze pagina ](../usecase/collections.md#limitations). De parameters hebben ook een verwachte indeling (bijvoorbeeld tekenreeks, decimaal, enz.). U moet deze verwachte formaten zorgvuldig respecteren. Verwijs naar dit [ gebruiksgeval ](../usecase/collections.md).

Hier zijn de belangrijkste stappen die worden vereist om een douaneactie te vormen:

1. Klik in de lijst **[!UICONTROL Actions]** op **[!UICONTROL Add]** om een nieuwe handeling te maken. Het deelvenster Handelingsconfiguratie wordt aan de rechterkant van het scherm geopend.

   ![](../assets/custom2.png)

1. Voer een naam in voor de handeling.

   >[!NOTE]
   >
   >Gebruik geen spaties of speciale tekens. Gebruik niet meer dan 30 tekens.

1. Voeg een beschrijving aan uw actie toe. Deze stap is optioneel.
1. Het aantal ritten dat deze handeling gebruikt, wordt weergegeven in het veld **[!UICONTROL Used in]** . U kunt op de knop **[!UICONTROL View journeys]** klikken om de lijst met ritten weer te geven die deze handeling gebruiken.
1. Definieer de verschillende **[!UICONTROL URL Configuration]** -parameters. Zie [deze pagina](../action/url-configuration.md).
1. Configureer de sectie **[!UICONTROL Authentication]** . Deze configuratie is het zelfde als voor gegevensbronnen.  Zie [deze sectie](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definieer de **[!UICONTROL Action parameters]** . Zie [deze pagina](../action/defining-the-message-parameters.md).
1. Klik op **[!UICONTROL Save]**.

   De aangepaste handeling is nu geconfigureerd en klaar om te worden gebruikt tijdens uw reizen. Zie [deze pagina](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >Wanneer een douaneactie in een reis wordt gebruikt, zijn de meeste parameters read-only. U kunt alleen de velden **[!UICONTROL Name]** , **[!UICONTROL Description]** , **[!UICONTROL URL]** en **[!UICONTROL Authentication]** wijzigen.
