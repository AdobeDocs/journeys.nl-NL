---
product: adobe campaign
solution: Journey Orchestration
title: 'Adobe Experience Platform-databron '
description: 'Leer hoe u de Adobe Experience Platform-gegevensbron configureert '
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 11%

---


# Adobe Experience Platform-databron {#concept_zrb_nqt_52b}

De Adobe Experience Platform-gegevensbron definieert de verbinding met de Real-Time Customer Profile Service. Deze gegevensbron is ingebouwd en vooraf geconfigureerd. Het kan niet worden verwijderd. Deze gegevensbron is ontworpen om gegevens van de Real-time Dienst van het Profiel van de Klant terug te winnen en te gebruiken (bijvoorbeeld, controleer of de persoon die een reis inging een vrouwelijk is). Hiermee kunt u de gegevens van het profiel en Events gebruiken. Voor meer informatie over de Real-time Dienst van het Profiel van de Klant, verwijs naar deze [pagina](https://docs.adobe.com/content/help/nl-NL/experience-platform/profile/home.html).

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

1. Selecteer een schema van **[!UICONTROL Schema]** drop-down. In dit veld worden de schema&#39;s voor profiel- en ervaringsgebeurtenissen weergegeven die beschikbaar zijn in de Adobe Experience Platform. Schema&#39;s maken wordt niet uitgevoerd in [!DNL Journey Orchestration]. Deze wordt uitgevoerd in de Adobe Experience Platform.
1. Selecteer de velden die u wilt gebruiken.
1. Definieer de duur van de cache.
1. Klik op **[!UICONTROL Save]**.

Wanneer u de cursor op de naam van een veldgroep plaatst, ziet u rechts twee pictogrammen. Hiermee kunt u de veldgroep verwijderen en dupliceren. Het pictogram **[!UICONTROL Delete]** is alleen beschikbaar als de veldgroep niet wordt gebruikt in een live of conceptreis (informatie in het veld **[!UICONTROL Used in]**).
