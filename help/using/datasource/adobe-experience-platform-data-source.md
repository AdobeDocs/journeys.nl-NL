---
title: 'Adobe Experience Platform-gegevensbron '
description: 'Leer hoe u de Adobe Experience Platform-gegevensbron configureert '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 0%

---


# Adobe Experience Platform data source {#concept_zrb_nqt_52b}

De Adobe Experience Platform-gegevensbron definieert de verbinding met de Real-Time Customer Profile Service. Deze gegevensbron is ingebouwd en vooraf geconfigureerd. Het kan niet worden verwijderd. Deze gegevensbron is ontworpen om gegevens van de Real-time Dienst van het Profiel van de Klant terug te winnen en te gebruiken (bijvoorbeeld, controleer of de persoon die een reis inging een vrouwelijk is). Hiermee kunt u de gegevens van het profiel en Events gebruiken. Raadpleeg deze [pagina](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)voor meer informatie over de realtime service voor klantprofielen.

>[!NOTE]
>
>U kunt de 1000 meest recente ervaringsgebeurtenissen ophalen die minder dan een jaar geleden zijn gemaakt.

Om de verbinding aan de Dienst van het Profiel van de Klant in real time toe te staan, moeten wij een sleutel gebruiken om een persoon, en een namespace te identificeren die contextualizes de sleutel. Hierdoor kunt u deze gegevensbron alleen gebruiken als uw reizen beginnen met een gebeurtenis die een sleutel en een naamruimte bevat. Zie [](../building-journeys/journey.md).

U kunt de vooraf geconfigureerde veldgroep met de naam &quot;ProfileFieldGroup&quot; bewerken, nieuwe veldgroepen toevoegen en de groepen verwijderen die niet worden gebruikt in concepten of livedagen. Zie [](../datasource/field-groups.md).

Hier zijn de belangrijkste stappen om gebiedsgroepen aan de ingebouwde gegevensbron toe te voegen.

1. Selecteer de Adobe Experience Platform-gegevensbron voor de build-in in de lijst met gegevensbronnen.

   Hiermee opent u het configuratievenster voor de gegevensbron aan de rechterkant van het scherm.

   ![](../assets/journey23.png)

1. Klik **[!UICONTROL Add a New Field Group]** om een nieuwe reeks velden op te halen. Zie [](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Selecteer een schema in de **[!UICONTROL Schema]** vervolgkeuzelijst. In dit veld worden de schema&#39;s voor profiel- en ervaringsgebeurtenissen weergegeven die beschikbaar zijn in de Adobe Experience Platform. Het maken van schema&#39;s wordt niet uitgevoerd in [!DNL Journey Orchestration]. Deze wordt uitgevoerd in de Adobe Experience Platform.
1. Selecteer de velden die u wilt gebruiken.
1. Definieer de duur van de cache.
1. Klik op **[!UICONTROL Save]**.

Wanneer u de cursor op de naam van een veldgroep plaatst, ziet u rechts twee pictogrammen. Hiermee kunt u de veldgroep verwijderen en dupliceren. Het **[!UICONTROL Delete]** pictogram is alleen beschikbaar als de veldgroep niet wordt gebruikt tijdens een live- of conceptreis (informatie in het **[!UICONTROL Used in]** veld).
