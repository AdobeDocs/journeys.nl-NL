---
product: adobe campaign
title: Aan de slag
description: Ontdek de belangrijkste stappen voor het instellen van Journey Orchestration en voor het samenstellen van uw eerste journey.
feature: Journeys
role: User
level: Beginner
exl-id: fe7bb5fe-7b5e-46da-8ef8-ae9401522c03
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 100%

---

# Aan de slag{#concept_y4b_4qt_52b}

In [!DNL Journey Orchestration] zijn er twee soorten gebruikers die elk hun eigen specifieke taken uitvoeren: de **technische gebruiker** en de **zakelijke gebruiker**. Gebruikerstoegang wordt beheerd via productprofielen en rechten. Raadpleeg [deze pagina](../about/access-management.md) om te leren hoe de gebruikerstoegang kan worden aangepast.

Hier volgen de belangrijkste stappen voor het configureren en gebruiken van [!DNL Journey Orchestration]:

1. **Een gebeurtenis configureren**

   U moet definiëren welke informatie wordt verwacht en hoe deze moet worden verwerkt. Deze configuratie is verplicht. Deze stap wordt uitgevoerd door een **technische gebruiker**.

   Raadpleeg [deze pagina](../event/about-events.md) voor meer informatie.

   ![](../assets/journey7.png)

1. **De databron configureren**

   U moet een verbinding definiëren met een systeem voor het ophalen van extra informatie die in uw journey’s wordt gebruikt, bijvoorbeeld in uw voorwaarden. Tijdens de provisioning wordt ook een ingebouwde Adobe Experience Platform-databron geconfigureerd. Deze stap is niet vereist als u alleen data gebruikt van de gebeurtenissen in uw journey. Deze stap wordt uitgevoerd door een **technische gebruiker**.

   Raadpleeg [deze pagina](../datasource/about-data-sources.md) voor meer informatie.

   ![](../assets/journey22.png)

1. **Een actie configureren**

   Als u een extern systeem gebruikt om uw berichten te verzenden, moet u de verbinding tussen dit systeem en [!DNL Journey Orchestration] configureren. Zie [deze pagina](../action/about-custom-action-configuration.md).

   Als u Adobe Campaign Standard gebruikt om berichten te verzenden, moet u de ingebouwde actie configureren. Zie [deze pagina](../action/working-with-adobe-campaign.md).

   Deze stappen worden uitgevoerd door een **technische gebruiker**.

   ![](../assets/custom2.png)

1. **Uw journey ontwerpen**

   Combineer de verschillende actie-, orkestratie- en gebeurtenisactiviteiten om uw kanaaloverschrijdende scenario’s met meerdere stappen te maken. Deze stap wordt uitgevoerd door een **zakelijke gebruiker**.

   Ga voor meer informatie naar [deze pagina](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **De journey testen en publiceren**

   U moet de journey valideren en activeren. Deze stap wordt uitgevoerd door een **zakelijke gebruiker**.

   Zie de pagina&#39;s [De journey testen](../building-journeys/testing-the-journey.md) en [De journey publiceren](../building-journeys/publishing-the-journey.md) voor meer informatie.

   ![](../assets/journeyuc2_32bis.png)

1. **Uw journey bewaken**

   Gebruik de speciale rapportagetools om de doeltreffendheid van uw journey te meten. Deze stap wordt uitgevoerd door een **zakelijke gebruiker**.

   Ga voor meer informatie naar [deze pagina](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)
