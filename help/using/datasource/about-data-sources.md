---
title: Gegevensbronnen
description: 'Leer hoe te om een gegevensbron te vormen '
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
source-wordcount: '356'
ht-degree: 0%

---


# Gegevensbronnen {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Gegevensbronnen"
>abstract="De gegevensbronconfiguratie wordt altijd uitgevoerd door een technische gebruiker. De gegevensbronconfiguratie staat u toe om een verbinding aan een systeem te bepalen om extra informatie terug te winnen die in uw reizen zal worden gebruikt, voor: voorwaardendefinitie, parameter en verpersoonlijkingsgegevens in acties, douane wachtte definitie, tijdzonedefinitie."

De gegevensbronconfiguratie staat u toe om een verbinding aan een systeem te bepalen om extra informatie terug te winnen die in uw reizen zal worden gebruikt, voor:

* [conditiedefinitie](../building-journeys/condition-activity.md)
* parameter- en personalisatiegegevens in [handelingen](../action/action.md)
* [aangepaste wachtdefinitie](../building-journeys/wait-activity.md#custom)
* [tijdzonedefinitie](../building-journeys/timezone-management.md)

Deze configuratie is niet vereist als uw reizen alleen lokale gegevens uit een gebeurtenislading gebruiken. Bijvoorbeeld, als uw reis uit een gebeurtenis wordt samengesteld die door een e-mailactiviteit wordt gevolgd die slechts gegevens van de gebeurtenis gebruikt, is er geen behoefte om een gegevensbron te vormen.

Er zijn twee soorten gegevensbronnen:

* De vooraf geconfigureerde gegevensbron van het Adobe Experience Platform die de verbinding met de Real-time service van het Profiel van de Klant definieert. Dit is een ingebouwde gegevensbron. Zie [](../datasource/adobe-experience-platform-data-source.md).
* De externe gegevensbronnen waarmee u een verbinding met externe systemen kunt definiëren. Dit zijn de methoden die u kunt maken. Zie [](../datasource/external-data-sources.md).

Voor elke gegevensbron definieert u de informatie die u wilt ophalen met behulp van veldgroepen. Veldgroepen zijn sets velden die uit een gegevensbron kunnen worden opgehaald. Zie [](../datasource/field-groups.md).

Voor meer informatie over hoe te om een Bron van de Gegevens van het Adobe Experience Platform en een externe gegevensbron te vormen en hoe te om gegevens in een reis te vinden en te gebruiken, deze [zelfstudievideo](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-data-sources.html)bekijken.

Hier zijn de belangrijkste stappen van de gegevensbronconfiguratie:

>[!NOTE]
>
>De gegevensbronconfiguratie wordt altijd uitgevoerd door een **technische gebruiker**.

1. Klik in het bovenste menu op de **[!UICONTROL Data Sources]** tab.

   De lijst met gegevensbronnen wordt weergegeven. Zie [](../about/user-interface.md) voor meer informatie over de interface.

   ![](../assets/journey18.png)

1. Vervolgens kunt u veldgroepen toevoegen aan de ingebouwde gegevensbron (zie [](../datasource/adobe-experience-platform-data-source.md)) of een nieuwe externe gegevensbron maken (zie [](../datasource/external-data-sources.md)) en gekoppelde veldgroepen (zie [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Klik op **[!UICONTROL Save]**.

   De gegevensbron is nu geconfigureerd en klaar om te worden gebruikt in uw reizen.
