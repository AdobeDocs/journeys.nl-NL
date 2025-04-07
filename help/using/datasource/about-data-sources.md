---
product: adobe campaign
title: Informatie over databronnen
description: Een databron configureren
feature: Journeys
role: User
level: Intermediate
exl-id: 2371d2c9-3035-46ac-9c76-755fb453c24e
source-git-commit: 4f6c5f9326b4d1cc4a1a02a036b51e4ad1ae68c4
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 73%

---

# Databronnen {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Databronnen"
>abstract="De gegevensbronconfiguratie staat u toe om een verbinding aan een systeem te bepalen om extra informatie terug te winnen die in uw reizen zal worden gebruikt."

Met de databronconfiguratie kunt u een verbinding met een systeem definiëren om extra informatie op te halen die in uw journey’s wordt gebruikt voor:

* [conditiedefinitie](../building-journeys/condition-activity.md)
* parameter- en personalisatiedata in [acties](../action/action.md)
* [aangepaste wachtdefinitie](../building-journeys/wait-activity.md#custom)
* [tijdzonedefinitie](../building-journeys/timezone-management.md)

Deze configuratie is niet vereist als uw journey’s alleen lokale data uit een gebeurtenispayload gebruiken. Als uw journey bijvoorbeeld bestaat uit een gebeurtenis gevolgd door een e-mailactiviteit die uitsluitend data van de gebeurtenis gebruikt, is het niet nodig om een databron te configureren.

Er zijn twee soorten databronnen:

* De vooraf geconfigureerde Adobe Experience Platform-databron die de verbinding met de realtimeservice van het klantprofiel definieert. Dit is een ingebouwde databron. Zie [deze pagina](../datasource/adobe-experience-platform-data-source.md).
* De externe databronnen waarmee u een verbinding met externe systemen kunt definiëren. Dit zijn databronnen die u kunt maken. Zie [deze pagina](../datasource/external-data-sources.md).

Voor elke databron definieert u de informatie die u wilt ophalen met behulp van veldengroepen. Veldengroepen zijn reeksen velden die uit een databron kunnen worden opgehaald. Zie [deze pagina](../datasource/field-groups.md).

Dit zijn de belangrijkste stappen voor de configuratie van databronnen:

>[!NOTE]
>
>De databronconfiguratie wordt altijd uitgevoerd door een **technische gebruiker**.

1. Selecteer **[!UICONTROL Admin]** in het menuvenster. Klik in de sectie **[!UICONTROL Data sources]** op **[!UICONTROL Manage]** .

   De lijst met databronnen wordt weergegeven. Zie [ deze pagina ](../about/user-interface.md) voor meer informatie over de interface.

   ![](../assets/journey18.png)

1. Dan kunt u of gebiedsgroepen aan de ingebouwde gegevensbron (zie [ deze pagina ](../datasource/adobe-experience-platform-data-source.md)) toevoegen of een nieuwe externe gegevensbron (zie [ deze pagina ](../datasource/external-data-sources.md)) en bijbehorende gebiedsgroepen (zie [ deze pagina ](../datasource/field-groups.md)) tot stand brengen.

   ![](../assets/journey23.png)

1. Klik op **[!UICONTROL Save]**.

   De databron is nu geconfigureerd en klaar om te worden gebruikt in uw journey’s.
