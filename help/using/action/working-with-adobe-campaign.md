---
product: adobe campaign
title: Werken met Adobe Campaign
description: Meer informatie over Adobe Campaign-acties
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: c49908d36ecbc68ae11b5621305f39dd59c67871
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 2%

---

# Werken met Adobe Campaign {#using_adobe_campaign}

## Adobe Campaign Standard gebruiken {#using_adobe_campaign_standard}

U kunt e-mails, pushberichten en SMS verzenden met de mogelijkheden voor Transactieberichten van Adobe Campaign Standard.

[!DNL Journey Orchestration] wordt geleverd met een actie buiten de doos die de verbinding aan Adobe Campaign Standard toestaat.

Het transactiemelding van de Campaign Standard en zijn bijbehorende gebeurtenis moeten worden gepubliceerd om in Journey Orchestration te worden gebruikt. Als de gebeurtenis wordt gepubliceerd maar het bericht niet is, zal het niet in de interface van Journey Orchestration zichtbaar zijn. Als het bericht wordt gepubliceerd maar zijn bijbehorende gebeurtenis is niet, zal het in de interface van Journey Orchestration zichtbaar zijn maar het zal niet bruikbaar zijn.

>[!NOTE]
>
>Zodra de Adobe Campaign Standard-integratie is ingesteld, wordt automatisch een regel van 13 aanroepen per seconde gedefinieerd voor Adobe Campaign Standard-acties. Dit komt overeen met de officiële schaal van Transactioneel Overseinen van Adobe Campaign Standard.
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
   >De host is &quot;.campagne.adobe.com&quot;, &quot;.campagne-sandbox.adobe.com&quot;, &quot;.campagne-demo.adobe.com&quot;, &quot;.ats.adobe.com&quot; of &quot;.adls.adobe.com&quot;.
   >
   >De URL begint met https.
   >
   >De ORG die aan deze Adobe Campaign Standard-instantie is gekoppeld, is gelijk aan de Journey Orchestration ORG.

Bij het ontwerpen van uw reis zijn drie acties beschikbaar in de categorie **[!UICONTROL Action]**: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (zie [Adobe Campaign-handelingen gebruiken](../building-journeys/using-adobe-campaign-actions.md)). **Met** gebeurtenis Reacties kunt u ook reageren op klikken op berichten, openen, enzovoort. (zie [Reactiegebeurtenissen](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Als u een derdesysteem gebruikt om berichten te verzenden, moet u een douaneactie toevoegen en vormen. Zie [Informatie over aangepaste actieconfiguratie](../action/about-custom-action-configuration.md).

## Adobe Campaign v7/v8 gebruiken {#using_adobe_campaign_v7_v8}

Deze integratie is beschikbaar voor Adobe Campaign Classic v7 vanaf versie 21.1 en Adobe Campaign v8. Hiermee kunt u e-mails, pushberichten en SMS verzenden met de mogelijkheden van Adobe Campaign Transaction Messaging.

De verbinding tussen de instanties van de Journey Orchestration en van de Campagne is opstelling door Adobe bij leveringstijd.

In deze [sectie](../usecase/campaign-v7-v8-use-case.md) wordt een gebruiksgeval van begin tot eind weergegeven.

Voor elke gevormde actie, is een actieactiviteit beschikbaar in het palet van de reisontwerper. Zie deze [sectie](../building-journeys/using-adobe-campaign-actions.md).

### Belangrijke opmerkingen

* Er is geen vertraging van berichten. Wij begrenzen het aantal berichten die over aan 50.000/uur kunnen worden verzonden die op onze huidige Campagne SLA wordt gebaseerd. Daarom dient reisorkestatie alleen te worden gebruikt in gevallen van eenmalig gebruik (individuele gevallen, niet segmenten).

* U moet één actie op het canvas per malplaatje vormen u wenst te gebruiken. U moet één actie in Journey Orchestration voor elke malplaatje vormen u om van Adobe Campaign wenst te gebruiken.

* Wij adviseren dat u een specifieke instantie van het Centrum van het Bericht gebruikt die voor deze integratie wordt ontvangen om het beïnvloeden van om het even welke andere verrichtingen van de Campagne te vermijden die u kunt hebben gaande. De marketingserver kan worden gehost of op locatie worden opgeslagen. De vereiste build is 21.1 Release Candidate of hoger.

* Er is geen bevestiging dat de lading of het bericht van de Campagne correct is.

* U kunt geen actie van de Campagne met een gebeurtenis van de segmentkwalificatie gebruiken.

### Vereisten

In Campagne, moet u een transactiebericht en zijn bijbehorende gebeurtenis tot stand brengen en publiceren. Raadpleeg de [Adobe Campaign-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

U kunt uw JSON-lading voor elk bericht samenstellen volgens het onderstaande patroon. U zult dan deze nuttige lading wanneer het vormen van de actie in Journey Orchestration (zie hieronder) kleven

Hier volgt een voorbeeld:

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **kanaal**: het kanaal dat voor uw transactiemalplaatje van de Campagne wordt bepaald
* **eventType**: de interne naam van uw Campagnegebeurtenis
* **ctx**: variabele die op de verpersoonlijking wordt gebaseerd u in uw bericht hebt.

### De handeling configureren

In Journey Orchestration, moet u één actie per transactiebericht vormen. Voer de volgende stappen uit:

1. Maak een nieuwe handeling. Zie deze [sectie](../action/action.md).
1. Voer een naam en beschrijving in.
1. Selecteer **Adobe Campaign Classic** in het veld **Actietype**.
1. Klik in het veld **Payload** en plak een voorbeeld van de JSON-lading die overeenkomt met het campagnebericht. Neem contact op met Adobe om deze lading op te halen.
1. Pas de verschillende velden aan op statisch of variabel, afhankelijk van de vraag of u ze wilt toewijzen op het canvas Reis. Bepaalde gebieden, zoals kanaalparameters voor e-mailadres en verpersoonlijkingsgebieden (ctx), wilt u waarschijnlijk bepaald als variabelen voor afbeelding in de context van de reis.
1. Klik **Opslaan**.

![](../assets/accintegration1.png)


