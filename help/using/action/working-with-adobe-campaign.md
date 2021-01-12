---
product: adobe campaign
solution: Journey Orchestration
title: Werken met Adobe Campaign
description: Meer informatie over Adobe Campaign-acties
translation-type: tm+mt
source-git-commit: 723c30865a5039bd68a8ac2e45d4c87a760e694d
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 4%

---


# Werken met Adobe Campaign {#using_adobe_campaign_standard}

U kunt e-mails, pushberichten en SMS verzenden met de mogelijkheden voor Transactieberichten van Adobe Campaign Standard.

[!DNL Journey Orchestration] wordt geleverd met een actie buiten de doos die de verbinding aan Adobe Campaign Standard toestaat.

Het transactiemelding van de Campaign Standard en zijn bijbehorende gebeurtenis moeten worden gepubliceerd om in Journey Orchestration te worden gebruikt. Als de gebeurtenis wordt gepubliceerd maar het bericht niet is, zal het niet in de interface van Journey Orchestration zichtbaar zijn. Als het bericht wordt gepubliceerd maar zijn bijbehorende gebeurtenis is niet, zal het in de interface van Journey Orchestration zichtbaar zijn maar het zal niet bruikbaar zijn.

>[!NOTE]
>
>Het Transactionele Overseinen van Adobe Campaign Standard heeft een schaal van 50 000 berichten per uur maximum over kanalen voor een bepaalde instantie. Om het risico van overbelasting te verminderen, adviseren wij dat u opstelling een **capping regel** voor de integratie van Campaign Standard.
>
>Lees meer over transactie overseinen SLAs in [Adobe Campaign Standard Productbeschrijving](https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html).

Hier volgen de stappen om het te configureren:

1. Klik in de lijst **[!UICONTROL Actions]** op de ingebouwde handeling **[!UICONTROL AdobeCampaignStandard]**. Het deelvenster Handelingsconfiguratie wordt aan de rechterkant van het scherm geopend.

   ![](../assets/actioncampaign.png)

1. Kopieer de Adobe Campaign Standard-instantie-URL en plak deze in het veld **[!UICONTROL URL]**.

1. Klik op **[!UICONTROL Test the instance URL]** om de geldigheid van de instantie te testen.

   >[!NOTE]
   >
   >Deze test verifieert dat:
   >
   >De host is &quot;.campagne.adobe.com&quot;, &quot;.campagne-sandbox.adobe.com&quot; of &quot;campagne-demo.adobe.com&quot;
   >
   >De URL begint met https.
   >
   >De ORG die aan deze Adobe Campaign Standard-instantie is gekoppeld, is gelijk aan de Journey Orchestration ORG.

Bij het ontwerpen van uw reis zijn drie acties beschikbaar in de categorie **[!UICONTROL Action]**: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (zie [Adobe Campaign-handelingen gebruiken](../building-journeys/using-adobe-campaign-actions.md)). **Met** gebeurtenis Reacties kunt u ook reageren op klikken op berichten, openen, enzovoort. (zie [Reactiegebeurtenissen](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Als u een derdesysteem gebruikt om berichten te verzenden, moet u een douaneactie toevoegen en vormen. Zie [Informatie over aangepaste actieconfiguratie](../action/about-custom-action-configuration.md).
