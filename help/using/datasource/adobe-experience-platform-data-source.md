---
product: adobe campaign
title: Adobe Experience Platform-databron
description: Leer hoe u de Adobe Experience Platform-gegevensbron configureert
feature: Journeys
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 8%

---

# Adobe Experience Platform-databron {#concept_zrb_nqt_52b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


De Adobe Experience Platform-gegevensbron definieert de verbinding met de Real-Time Customer Profile Service. Deze gegevensbron is ingebouwd en vooraf geconfigureerd. Het kan niet worden verwijderd. Deze gegevensbron is ontworpen om gegevens van de Real-time Dienst van het Profiel van de Klant terug te winnen en te gebruiken (bijvoorbeeld, controleer of de persoon die een reis inging een vrouwelijk is). Hiermee kunt u de gegevens van het profiel en de gegevens van Experience Events gebruiken. Voor meer informatie over de Echte Dienst van het Profiel van de Klant, verwijs naar deze [&#x200B; pagina &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=nl).

>[!NOTE]
>
>U kunt de 1000 meest recente ervaringsgebeurtenissen ophalen die minder dan een jaar geleden zijn gemaakt.

Om de verbinding aan de Dienst van het Profiel van de Klant in real time toe te staan, moeten wij een sleutel gebruiken om een persoon, en een namespace te identificeren die contextualizes de sleutel. Hierdoor kunt u deze gegevensbron alleen gebruiken als uw reizen beginnen met een gebeurtenis die een sleutel en een naamruimte bevat. Zie [deze pagina](../building-journeys/journey.md).

U kunt de vooraf geconfigureerde veldgroep met de naam &quot;ProfileFieldGroup&quot; bewerken, nieuwe veldgroepen toevoegen en de groepen verwijderen die niet worden gebruikt in concepten of livedagen. Zie [deze pagina](../datasource/field-groups.md).

Hier zijn de belangrijkste stappen om gebiedsgroepen aan de ingebouwde gegevensbron toe te voegen.

1. Selecteer de Adobe Experience Platform-gegevensbron voor de build-in in de lijst met gegevensbronnen.

   Hiermee opent u het configuratiedeelvenster voor de databron aan de rechterkant van het scherm.

   ![](../assets/journey23.png)

1. Klik op **[!UICONTROL Add a New Field Group]** om een nieuwe reeks velden op te halen. Zie [deze pagina](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Selecteer een schema in de vervolgkeuzelijst **[!UICONTROL Schema]** . In dit veld worden de schema&#39;s voor profiel- en ervaringsgebeurtenissen weergegeven die beschikbaar zijn in de Adobe Experience Platform. Schema&#39;s maken wordt niet uitgevoerd in [!DNL Journey Orchestration] . Het wordt uitgevoerd in de Adobe Experience Platform.
1. Selecteer de velden die u wilt gebruiken.
1. Klik op **[!UICONTROL Save]** .

Wanneer u de cursor op de naam van een veldgroep plaatst, ziet u rechts twee pictogrammen. Hiermee kunt u de veldgroep verwijderen en dupliceren. Het pictogram **[!UICONTROL Delete]** is alleen beschikbaar als de veldgroep niet wordt gebruikt tijdens een live of conceptrit (informatie wordt weergegeven in het veld **[!UICONTROL Used in]** ).
