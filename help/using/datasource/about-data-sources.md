---
title: Informatie over databronnen
description: 'Een databron configureren '
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
source-wordcount: '356'
ht-degree: 100%

---


# Informatie over databronnen{#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Informatie over databronnen"
>abstract="De databronconfiguratie wordt altijd uitgevoerd door een technische gebruiker. Met de databronconfiguratie kunt u een verbinding met een systeem definiëren om extra informatie op te halen die in uw journey’s wordt gebruikt voor parameter- en personalisatiedata in acties en het definiëren van voorwaarden, tijdzones en aangepaste wachttijden."

Met de databronconfiguratie kunt u een verbinding met een systeem definiëren om extra informatie op te halen die in uw journey’s wordt gebruikt voor:

* [het definiëren van voorwaarden](../building-journeys/condition-activity.md)
* parameter- en personalisatiedata in [acties](../action/action.md)
* [het definiëren van aangepaste wachttijden](../building-journeys/wait-activity.md#custom)
* [het definiëren van tijdzones](../building-journeys/timezone-management.md)

Deze configuratie is niet vereist als uw journey’s alleen lokale data uit een gebeurtenispayload gebruiken. Als uw journey bijvoorbeeld bestaat uit een gebeurtenis gevolgd door een e-mailactiviteit die uitsluitend data van de gebeurtenis gebruikt, is het niet nodig om een databron te configureren.

Er zijn twee soorten databronnen:

* De vooraf geconfigureerde Adobe Experience Platform-databron die de verbinding met de realtimeservice van het klantprofiel definieert. Dit is een ingebouwde databron. Zie [](../datasource/adobe-experience-platform-data-source.md).
* De externe databronnen waarmee u een verbinding met externe systemen kunt definiëren. Dit zijn databronnen die u kunt maken. Zie [](../datasource/external-data-sources.md).

Voor elke databron definieert u de informatie die u wilt ophalen met behulp van veldengroepen. Veldengroepen zijn reeksen velden die uit een databron kunnen worden opgehaald. Zie [](../datasource/field-groups.md).

Voor meer informatie over het configureren van een Adobe Experience Platform-databron en een externe databron en hoe u gegevens in een journey kunt vinden en gebruiken, bekijkt u deze [zelfstudievideo](https://docs.adobe.com/content/help/nl-NL/journey-orchestration-learn/tutorials/configure-data-sources.html).

Dit zijn de belangrijkste stappen voor de configuratie van databronnen:

>[!NOTE]
>
>De databronconfiguratie wordt altijd uitgevoerd door een **technische gebruiker**.

1. Klik in het bovenste menu op het tabblad **[!UICONTROL Data Sources]**.

   De lijst met databronnen wordt weergegeven. Zie [](../about/user-interface.md) voor meer informatie over de interface.

   ![](../assets/journey18.png)

1. Vervolgens kunt u veldengroepen toevoegen aan de ingebouwde databron (zie [](../datasource/adobe-experience-platform-data-source.md)) of een nieuwe externe databron maken (zie [](../datasource/external-data-sources.md)) en gekoppelde veldengroepen (zie [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Klik op **[!UICONTROL Save]**.

   De databron is nu geconfigureerd en klaar om te worden gebruikt in uw journey’s.
