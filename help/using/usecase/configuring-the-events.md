---
title: Gebeurtenissen configureren
description: Leer hoe te om de gebeurtenissen voor reis geavanceerd gebruiksgeval te vormen
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%

---


# Gebeurtenissen configureren {#concept_sbp_5cy_w2b}

In ons scenario moeten we telkens een evenement ontvangen wanneer een persoon het hotel Marlton en het restaurant binnenkomt. De **technische gebruiker** moet de twee gebeurtenissen vormen wij het systeem willen om aan in onze reis te luisteren.

Raadpleeg voor meer informatie over gebeurtenisconfiguratie [](../event/about-events.md).

1. Klik in het bovenste menu op het **[!UICONTROL Events]** tabblad en klik **[!UICONTROL Add]** om een nieuwe gebeurtenis te maken.

   ![](../assets/journeyuc1_1.png)

1. U voert de naam in zonder spaties of speciale tekens: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

<!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc2_3.png" placement="break" width="800" id="image_is5_2sn_z2b"/></li-->

1. Vervolgens selecteert u het schema en definieert u de lading die voor deze gebeurtenis wordt verwacht. We selecteren de velden die nodig zijn in het genormaliseerde XDM-model. We hebben de Experience Cloud-id nodig om de persoon te identificeren in de realtime database voor klantprofielen: &quot;endUserIDs > _experience > mcid > id&quot;.

   Het registratietoken is ook nodig voor het verzenden van pushberichten: &quot;_experience > campagne > bericht > profiel > pushNotificationTokens > token&quot;

   Er wordt automatisch een id voor deze gebeurtenis gegenereerd. Deze id wordt opgeslagen in het **[!UICONTROL eventID]** veld (&quot;_experience > Campagne > Orchestratie > eventID&quot;). Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. In ons gebruiksgeval, wordt dit ID gebruikt om de bakenplaats te identificeren. Elke keer dat een persoon in de buurt van het lobby-baken loopt, wordt een gebeurtenis verzonden die deze specifieke gebeurtenis-id bevat. Hetzelfde beginsel geldt voor de restaurantbakenevenementen. Dit staat het systeem toe om te weten welk baken de gebeurtenis teweegbracht die verzendt.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >De lijst met velden verschilt per schema. Volgens de schemadefinitie zijn sommige velden mogelijk verplicht en vooraf geselecteerd.

1. We moeten een naamruimte selecteren. Een naamruimte wordt vooraf geselecteerd op basis van schema-eigenschappen. U kunt de voorinstelling behouden. Zie voor meer informatie over naamruimten [](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Een sleutel wordt vooraf geselecteerd gebaseerd op schemaeigenschappen en namespace geselecteerd. Je kunt het houden.

   ![](../assets/journeyuc2_4bis.png)

1. Klik op **[!UICONTROL Save]**.

1. Klik op het **[!UICONTROL View Payload]** pictogram om een voorvertoning weer te geven van de lading die door het systeem wordt verwacht en deze te delen met de persoon die verantwoordelijk is voor het verzenden van de gebeurtenis.  Deze nuttige lading zal in postback van de Mobiele het beleidsconsole van de Diensten moeten worden gevormd.

   ![](../assets/journeyuc2_5.png)

Maak op dezelfde manier de gebeurtenis &quot;RestaurantBeacon&quot;. Uw twee baken-gebeurtenissen worden gecreëerd en kunnen nu worden gebruikt op onze reis. U moet nu de mobiele toepassing vormen zodat het de verwachte nuttige lading naar het Streaming Ingestie APIs eindpunt kan verzenden. Zie [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
