---
title: De gebeurtenis configureren
description: Leer hoe u de gebeurtenis configureert voor het eenvoudige gebruiksgeval van de reis
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
source-wordcount: '351'
ht-degree: 0%

---


# De gebeurtenis configureren{#concept_y44_hcy_w2b}

In ons scenario, moeten wij een gebeurtenis ontvangen telkens als een persoon dichtbij een baken loopt dat naast de spanwijdte wordt geplaatst. De **technische gebruiker** moet de gebeurtenis vormen het systeem aan in onze reis zal luisteren.

Raadpleeg voor meer informatie over gebeurtenisconfiguratie [](../event/about-events.md).

1. Klik in het bovenste menu op het **[!UICONTROL Events]** tabblad en klik **[!UICONTROL Add]** om een nieuwe gebeurtenis te maken.

   ![](../assets/journeyuc1_1.png)

1. De naam wordt ingevoerd zonder spaties of speciale tekens: &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

   <!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc1_4.png" placement="break" width="800" id="image_qgr_2mn_z2b"/></li-->

1. Vervolgens selecteert u het schema en definieert u de lading die voor deze gebeurtenis wordt verwacht. We selecteren de velden die nodig zijn in het genormaliseerde XDM-model. We hebben de Experience Cloud-id nodig om de persoon te identificeren in de realtime database voor klantprofielen: _endUserIDs > ervaring > mcid > identiteitskaart_. Er wordt automatisch een id voor deze gebeurtenis gegenereerd. Deze id wordt opgeslagen in het **[!UICONTROL eventID]** veld (_ervaring > Campagne > Orchestratie > eventID_). Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. In ons gebruiksgeval, wordt dit ID gebruikt om de bakenplaats te identificeren. Elke keer dat een persoon in de buurt van de spa-baken loopt, wordt een gebeurtenis verzonden die deze specifieke gebeurtenis-id bevat. Dit staat het systeem toe om te weten welk baken de gebeurtenis teweegbracht die verzendt.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >De lijst met velden verschilt per schema. Volgens de schemadefinitie zijn sommige velden mogelijk verplicht en vooraf geselecteerd.

1. We moeten een naamruimte selecteren. Een naamruimte wordt vooraf geselecteerd op basis van schema-eigenschappen. U kunt de voorinstelling behouden. Zie voor meer informatie over naamruimten [](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. Een sleutel wordt vooraf geselecteerd gebaseerd op schemaeigenschappen en namespace geselecteerd. Je kunt het houden.

   ![](../assets/journeyuc1_5.png)

1. Klik op **[!UICONTROL Save]**.

1. Klik op het **[!UICONTROL View Payload]** pictogram om een voorvertoning weer te geven van de lading die door het systeem wordt verwacht en deze te delen met de persoon die verantwoordelijk is voor het verzenden van de gebeurtenis. Deze nuttige lading zal in postback van de Mobiele het beleidsconsole van de Diensten moeten worden gevormd.

   ![](../assets/journeyuc1_7.png)

   Het evenement is klaar om op reis te worden gebruikt. U moet nu de mobiele toepassing vormen zodat het de verwachte nuttige lading naar het Streaming Ingestie APIs eindpunt kan verzenden. Zie [](../event/additional-steps-to-send-events-to-journey-orchestration.md).