---
product: adobe campaign
solution: Journey Orchestration
title: Een gebeurtenis maken
description: Leer hoe u een gebeurtenis maakt
feature: Reizen
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 53%

---


# Een nieuwe gebeurtenis maken {#section_tbk_5qt_pgb}

Dit zijn de belangrijkste stappen voor het configureren van een nieuwe gebeurtenis:

1. Klik in het bovenste menu op het tabblad **[!UICONTROL Events]**. De lijst met gebeurtenissen wordt weergegeven. Raadpleeg [deze pagina](../about/user-interface.md) voor meer informatie over de interface.

   ![](../assets/journey5.png)

1. Klik op **[!UICONTROL Add]** om een nieuwe gebeurtenis te maken. Het deelvenster voor gebeurtenisconfiguratie wordt aan de rechterkant van het scherm geopend. Voer een naam in voor de gebeurtenis. U kunt ook een beschrijving toevoegen.

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >Gebruik geen spaties of speciale tekens. Gebruik niet meer dan 30 tekens.

1. Selecteer in het veld **[!UICONTROL Event ID type]** het gebeurtenistype dat u wilt gebruiken.

   ![](../assets/journey6bis.png)

   * **Op regels** gebaseerde gebeurtenissen: dit type gebeurtenis genereert geen eventID. In het **Voorwaarde identiteitskaart van de Gebeurtenis** gebied, bepaalt u eenvoudig een regel die door het systeem zal worden gebruikt om de relevante gebeurtenissen te identificeren die uw reizen zullen teweegbrengen. Deze regel kan worden gebaseerd op elk veld dat beschikbaar is in de gebeurtenislading, bijvoorbeeld de locatie van het profiel of het aantal items dat is toegevoegd aan het winkelwagentje van het profiel.

   * **System-** generateDefents: voor dit type is een eventID vereist. Dit veld eventID wordt automatisch gegenereerd wanneer de gebeurtenis wordt gemaakt en toegevoegd aan de voorvertoning van de laadbewerking. Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten overgaan beschikbaar in de voorproef van de lading. Zie [deze sectie](../event/previewing-the-payload.md).
   >[!NOTE]
   >
   >Lees meer over gebeurtenistypen in [deze sectie](../event/about-events.md).
1. Het aantal journey’s dat deze gebeurtenis gebruikt, wordt in het veld **[!UICONTROL Used in]** weergegeven. U kunt klikken op het pictogram **[!UICONTROL View journeys]** om de lijst weer te geven met journey’s die deze gebeurtenis gebruiken.
1. Definieer het schema en de payloadvelden: hier selecteert u de gebeurtenisinformatie (gewoonlijk een payload genoemd) die [!DNL Journey Orchestration] verwacht te ontvangen. U kunt deze informatie vervolgens gebruiken tijdens uw journey. Zie [deze pagina](../event/defining-the-payload-fields.md).
   >[!NOTE]
   >
   >Wanneer u het type **[!UICONTROL System Generated]** selecteert, zijn slechts schema&#39;s beschikbaar die het eventID typemengsel hebben. Wanneer u het type **[!UICONTROL Rule Based]** selecteert, zijn alle schema&#39;s van de Gebeurtenis van de Ervaring beschikbaar.

1. Voor op regel-gebaseerde gebeurtenissen, klik binnen het **[!UICONTROL Event ID condition]** gebied. Gebruikend de eenvoudige uitdrukkingsredacteur, bepaal de voorwaarde die door het systeem zal worden gebruikt om de gebeurtenissen te identificeren die uw reis zullen teweegbrengen.
   ![](../assets/alpha-event6.png)

   In ons voorbeeld schreven we een voorwaarde op basis van de stad van het profiel. Dit betekent dat wanneer het systeem een gebeurtenis ontvangt die deze voorwaarde (**[!UICONTROL City]** gebied en **[!UICONTROL Paris]** waarde) aanpast, het het aan Journey Orchestration zal overgaan.

1. Voeg een naamruimte toe. Deze stap is optioneel, maar wordt aangeraden, omdat u door het toevoegen van een naamruimte gegevens kunt gebruiken die zijn opgeslagen in de real-timeklantprofielservice. U definieert zo het type sleutel van de gebeurtenis. Zie [deze pagina](../event/selecting-the-namespace.md).
1. Sleutel definiëren: kies een veld in uw payloadvelden of definieer een formule om de persoon te identificeren die aan de gebeurtenis is gekoppeld. Deze sleutel wordt automatisch ingesteld (maar kan nog steeds worden bewerkt) als u een naamruimte selecteert. [!DNL Journey Orchestration] kiest namelijk de sleutel die moet overeenkomen met de naamruimte (als u bijvoorbeeld een naamruimte voor e-mail selecteert, wordt de e-mailsleutel geselecteerd). Zie [deze pagina](../event/defining-the-event-key.md).
1. Voor door het systeem gegenereerde gebeurtenissen kunt u een voorwaarde toevoegen. Deze stap is optioneel. Hiermee stelt u het systeem in staat alleen gebeurtenissen te verwerken die aan de voorwaarde voldoen. De voorwaarde kan alleen worden gebaseerd op informatie in de gebeurtenis. Zie [deze pagina](../event/adding-a-condition.md).
1. Klik op **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   De gebeurtenis is nu geconfigureerd en klaar om in een journey worden gezet. Er zijn aanvullende configuratiestappen nodig om gebeurtenissen te ontvangen. Zie [deze pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).
