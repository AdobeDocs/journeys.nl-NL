---
title: Werken met Adobe Campaign
description: Meer informatie over Adobe Campaign-acties
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
source-git-commit: 4f7cc4da51a93019b5a296003c51d4bee6724498
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 2%

---


# Werken met Adobe Campaign {#using_adobe_campaign_standard}

U kunt e-mails, pushberichten en SMS verzenden met de mogelijkheden voor Transactieberichten van Adobe Campaign Standard.

[!DNL Journey Orchestration] wordt geleverd met een actie buiten de doos die de verbinding aan Adobe Campaign Standard toestaat.

Het transactiemelding van de Campaign Standard en zijn bijbehorende gebeurtenis moeten worden gepubliceerd om in Journey Orchestration te worden gebruikt. Als de gebeurtenis wordt gepubliceerd maar het bericht niet is, zal het niet in de interface van Journey Orchestration zichtbaar zijn. Als het bericht wordt gepubliceerd maar zijn bijbehorende gebeurtenis is niet, zal het in de interface van Journey Orchestration zichtbaar zijn maar het zal niet bruikbaar zijn.

>[!NOTE]
>
>Om het Transactionele Overseinen van Adobe Campaign Standard te vermijden, wordt het geadviseerd om een **afschilderingsregel** voor de integratie van de Campaign Standard te plaatsen.
>
>Meer informatie over SLA&#39;s voor transactieberichten vindt u in de productbeschrijving [van](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)Adobe Campaign Standard.

Hier volgen de stappen om het te configureren:

1. Klik in de **[!UICONTROL Actions]** lijst op de ingebouwde **[!UICONTROL AdobeCampaignStandard]** actie. Het deelvenster Handelingsconfiguratie wordt aan de rechterkant van het scherm geopend.

   ![](../assets/actioncampaign.png)

1. Kopieer de Adobe Campaign Standard-instantie-URL en plak deze in het **[!UICONTROL URL]** veld.

1. Klik op het pictogram **[!UICONTROL Test the instance URL]** om de geldigheid van de instantie te testen.

   >[!NOTE]
   >
   >Deze test verifieert dat:
   >
   >De host is &quot;.campagne.adobe.com&quot; of &quot;.campagne-sandbox.adobe.com&quot;,
   >
   >De URL begint met https.
   >
   >De ORG die aan deze Adobe Campaign Standard-instantie is gekoppeld, is gelijk aan de Journey Orchestration ORG.

Wanneer het ontwerpen van uw reis, zullen drie acties in de **[!UICONTROL Action]** categorie beschikbaar zijn: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (zie [Adobe Campaign-handelingen](../building-journeys/using-adobe-campaign-actions.md)gebruiken). **Met de gebeurtenis** Reacties kunt u ook reageren op berichtklikken, wordt geopend, enzovoort. (zie [Reacties gebeurtenissen](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Als u een derdesysteem gebruikt om berichten te verzenden, moet u een douaneactie toevoegen en vormen. See [About custom action configuration](../action/about-custom-action-configuration.md).
