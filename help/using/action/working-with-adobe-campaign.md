---
product: adobe campaign
title: Werken met Adobe Campaign
description: Meer informatie over Adobe Campaign-acties
feature: Journeys
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---

# Werken met Adobe Campaign Standard {#using_adobe_campaign_standard}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


U kunt e-mails, pushberichten en SMS verzenden met de mogelijkheden voor Transactieberichten van Adobe Campaign Standard.

[!DNL Journey Orchestration] wordt geleverd met een actie buiten de doos die de verbinding aan Adobe Campaign Standard toestaat.

Het Campaign Standard-transactiebericht en de bijbehorende gebeurtenis moeten worden gepubliceerd om in Journey Orchestration te kunnen worden gebruikt. Als de gebeurtenis wordt gepubliceerd maar het bericht niet is, is het niet zichtbaar in de interface van Journey Orchestration. Als het bericht wordt gepubliceerd maar zijn bijbehorende gebeurtenis niet, zal het in de interface van Journey Orchestration zichtbaar zijn maar het zal niet bruikbaar zijn.

>[!NOTE]
>
>Zodra de Adobe Campaign Standard-integratie is ingesteld, wordt automatisch een afluisterregel van 4000 oproepen per 5 minuten gedefinieerd voor Adobe Campaign Standard-acties. Dit komt overeen met de officiële schaal van Transactioneel Overseinen van Adobe Campaign Standard.
>
>Lees meer over transactionele overseinen SLAs in [ de Beschrijving van het Product van Adobe Campaign Standard ](https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html).

Hier volgen de stappen om het te configureren:

1. Klik in de lijst **[!UICONTROL Actions]** op de ingebouwde handeling **[!UICONTROL AdobeCampaignStandard]** . Het deelvenster Handelingsconfiguratie wordt aan de rechterkant van het scherm geopend.

   ![](../assets/actioncampaign.png)

1. Kopieer de Adobe Campaign Standard-instantie-URL en plak deze in het veld **[!UICONTROL URL]** .

1. Klik op **[!UICONTROL Test the instance URL]** om de geldigheid van de instantie te testen.

   >[!NOTE]
   >
   >Deze test verifieert dat:
   >
   >De host is &quot;.campagne.adobe.com&quot;, &quot;.campagne-sandbox.adobe.com&quot;, &quot;.campagne-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; of &quot;.adls.adobe.com&quot;.
   >
   >De URL begint met https.
   >
   >De ORG die aan deze Adobe Campaign Standard-instantie is gekoppeld, is gelijk aan de Journey Orchestration ORG.

Wanneer het ontwerpen van uw reis, zullen drie acties in de **[!UICONTROL Action]** categorie beschikbaar zijn: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (zie [ Gebruikend de acties van Adobe Campaign ](../building-journeys/using-adobe-campaign-actions.md)). **de gebeurtenis van Reacties** zal u ook toestaan om op bericht te reageren klikt, opent, enz. (zie [ gebeurtenissen van Reacties ](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Als u een derdesysteem gebruikt om berichten te verzenden, moet u een douaneactie toevoegen en vormen. Zie [ Ongeveer de configuratie van de douaneactie ](../action/about-custom-action-configuration.md).
