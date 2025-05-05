---
product: adobe campaign
title: Een gebeurtenis maken
description: Leer hoe u een gebeurtenis maakt
feature: Journeys
role: User
level: Intermediate
exl-id: 2ae8854a-c3e7-469d-9f89-25b54bc3e894
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 47%

---

# Een nieuwe gebeurtenis maken {#section_tbk_5qt_pgb}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Dit zijn de belangrijkste stappen voor het configureren van een nieuwe gebeurtenis:

1. Klik in het bovenste menu op het tabblad **[!UICONTROL Events]**. De lijst met gebeurtenissen wordt weergegeven. Verwijs naar [ deze pagina ](../about/user-interface.md) voor meer informatie over de interface.

   ![](../assets/journey5.png)

1. Klik op **[!UICONTROL Add]** om een nieuwe gebeurtenis te maken. Het deelvenster voor gebeurtenisconfiguratie wordt aan de rechterkant van het scherm geopend. Voer een naam in voor de gebeurtenis. U kunt ook een beschrijving toevoegen.

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >Gebruik geen spaties of speciale tekens. Gebruik niet meer dan 30 tekens.

1. Selecteer in het veld **[!UICONTROL Event ID type]** het gebeurtenistype dat u wilt gebruiken.

   ![](../assets/journey6bis.png)

   * **Op regels gebaseerde** gebeurtenissen: dit type gebeurtenis genereert geen eventID. Op het **gebied van identiteitskaart van de Gebeurtenis 0&rbrace;, bepaalt u eenvoudig een regel die door het systeem zal worden gebruikt om de relevante gebeurtenissen te identificeren die uw reizen zullen teweegbrengen.** Deze regel kan zijn gebaseerd op elk veld dat beschikbaar is in de gebeurtenispayload, bijvoorbeeld de locatie van het profiel of het aantal items dat is toegevoegd aan de winkelwagen van het profiel.

   * **systeem-geproduceerde** gebeurtenissen: dit type vereist een eventID. Dit veld eventID wordt automatisch gegenereerd wanneer de gebeurtenis wordt gemaakt en toegevoegd aan de voorvertoning van de laadbewerking. Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten overgaan beschikbaar in de voorproef van de lading. Zie [deze sectie](../event/previewing-the-payload.md).

   >[!NOTE]
   >
   >Lees meer op gebeurtenistypen in [ deze sectie ](../event/about-events.md).
1. Het aantal journey’s dat deze gebeurtenis gebruikt, wordt in het veld **[!UICONTROL Used in]** weergegeven. U kunt klikken op het pictogram **[!UICONTROL View journeys]** om de lijst weer te geven met journey’s die deze gebeurtenis gebruiken.
1. Definieer het schema en de payloadvelden: hier selecteert u de gebeurtenisinformatie (gewoonlijk een payload genoemd) die [!DNL Journey Orchestration] verwacht te ontvangen. U kunt deze informatie vervolgens gebruiken tijdens uw journey. Zie [deze pagina](../event/defining-the-payload-fields.md).
   >[!NOTE]
   >
   >Wanneer u het type **[!UICONTROL System Generated]** selecteert, zijn alleen schema&#39;s beschikbaar die het type eventID-mix hebben. Wanneer u het type **[!UICONTROL Rule Based]** selecteert, zijn alle schema&#39;s voor Experience Event beschikbaar.

1. Voor op regel-gebaseerde gebeurtenissen, klik binnen het **[!UICONTROL Event ID condition]** gebied. Gebruikend de eenvoudige uitdrukkingsredacteur, bepaal de voorwaarde die door het systeem zal worden gebruikt om de gebeurtenissen te identificeren die uw reis zullen teweegbrengen.
   ![](../assets/alpha-event6.png)

   In ons voorbeeld schreven we een voorwaarde op basis van de stad van het profiel. Dit houdt in dat wanneer het systeem een gebeurtenis ontvangt die overeenkomt met deze voorwaarde (**[!UICONTROL City]** field en **[!UICONTROL Paris]** value), deze wordt doorgegeven aan Journey Orchestration.

   >[!NOTE]
   >
   >De geavanceerde expressie-editor is niet beschikbaar wanneer u de **[!UICONTROL Event ID condition]** definieert. In de eenvoudige expressie-editor zijn niet alle operatoren beschikbaar, maar zijn ze afhankelijk van het gegevenstype. Voor een tekenreekstype kunt u bijvoorbeeld &quot;contains&quot; of &quot;equal to&quot; gebruiken.

1. Voeg een naamruimte toe. Deze stap is optioneel, maar wordt aangeraden, omdat u door het toevoegen van een naamruimte gegevens kunt gebruiken die zijn opgeslagen in de real-timeklantprofielservice. U definieert zo het type sleutel van de gebeurtenis. Zie [deze pagina](../event/selecting-the-namespace.md).
1. Sleutel definiëren: kies een veld in uw payloadvelden of definieer een formule om de persoon te identificeren die aan de gebeurtenis is gekoppeld. Deze sleutel wordt automatisch ingesteld (maar kan nog steeds worden bewerkt) als u een naamruimte selecteert. [!DNL Journey Orchestration] kiest namelijk de sleutel die moet overeenkomen met de naamruimte (als u bijvoorbeeld een naamruimte voor e-mail selecteert, wordt de e-mailsleutel geselecteerd). Zie [deze pagina](../event/defining-the-event-key.md).
1. Klik op **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   De gebeurtenis is nu geconfigureerd en klaar om in een journey worden gezet. Er zijn aanvullende configuratiestappen nodig om gebeurtenissen te ontvangen. Zie [deze pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).
