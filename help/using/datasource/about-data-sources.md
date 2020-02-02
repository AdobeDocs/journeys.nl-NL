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
source-git-commit: d0a7bbb43ae62fbdcf7ef34b0b56b1d437047ad2

---


# Gegevensbronnen {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id=&quot;jo_datasources&quot;
>title=&quot;Gegevensbronnen&quot;
>abstract=&quot;De gegevensbronconfiguratie wordt altijd uitgevoerd door een technische gebruiker. De gegevensbronconfiguratie staat u toe om een verbinding aan een systeem te bepalen om extra informatie terug te winnen die in uw reizen zal worden gebruikt, voor: voorwaardendefinitie, parameter en verpersoonlijkingsgegevens in acties, douane wachttijddefinitie, definitie van de douanetijdzone.&quot;

De gegevensbronconfiguratie wordt altijd uitgevoerd door een **technische gebruiker**.

De gegevensbronconfiguratie staat u toe om een verbinding aan een systeem te bepalen om extra informatie terug te winnen die in uw reizen zal worden gebruikt, voor:

* conditiedefinitie
* parameter- en personalisatiegegevens in handelingen
* aangepaste wachtdefinitie
* definitie van aangepaste tijdzone

Deze configuratie is niet vereist als uw reizen alleen lokale gegevens uit een gebeurtenislading gebruiken. Bijvoorbeeld, als uw reis uit een gebeurtenis wordt samengesteld die door een e-mailactiviteit wordt gevolgd die slechts gegevens van de gebeurtenis gebruikt, is er geen behoefte om een gegevensbron te vormen.

Er zijn twee soorten gegevensbronnen:

* De vooraf geconfigureerde gegevensbron van het ervaringsplatform die de verbinding met de Real-Time Dienst van het Profiel van de Klant bepaalt. Dit is een ingebouwde gegevensbron. Zie [](../datasource/adobe-experience-platform-data-source.md).
* De externe gegevensbronnen waarmee u een verbinding met externe systemen kunt definiëren. Dit zijn de methoden die u kunt maken. Zie [](../datasource/external-data-sources.md).

Voor elke gegevensbron definieert u de informatie die u wilt ophalen met behulp van veldgroepen. Zie [](../datasource/field-groups.md).

Hier zijn de belangrijkste stappen van de gegevensbronconfiguratie:

1. Klik in het bovenste menu op de **[!UICONTROL Data Sources]**tab.

   De lijst met gegevensbronnen wordt weergegeven. Zie [](../about/user-interface.md) voor meer informatie over de interface.

   ![](../assets/journey18.png)

1. Vervolgens kunt u veldgroepen toevoegen aan de ingebouwde gegevensbron (zie [](../datasource/adobe-experience-platform-data-source.md)) of een nieuwe externe gegevensbron maken (zie [](../datasource/external-data-sources.md)) en gekoppelde veldgroepen (zie [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Klik **[!UICONTROL Save]**.

   De gegevensbron is nu geconfigureerd en klaar om te worden gebruikt in uw reizen.
