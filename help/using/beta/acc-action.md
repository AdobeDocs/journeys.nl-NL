---
product: adobe campaign
solution: Journey Orchestration
title: Over Campaign Classic-integratie
description: Meer informatie over Campaign Classic-integratie
hide: true
hidefromtoc: true
feature: Reizen
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 0%

---


# Integreren met Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Dankzij deze integratie kunt u e-mails, pushberichten en SMS verzenden via de mogelijkheden van Adobe Campaign Classic Transaction Messaging.

De verbinding tussen de instanties van de Journey Orchestration en van de Campaign Classic is opstelling door Adobe bij leveringstijd.

>[!CAUTION]
>
> Deze integratie wordt vrijgegeven als privé bèta. Het is niet beschikbaar voor alle klanten van de Journey Orchestration.

## Belangrijke opmerkingen

* Er is geen vertraging van berichten. Wij begrenzen het aantal berichten die over naar 50.000/uur kunnen worden verzonden die op onze huidige Campaign Classic SLA wordt gebaseerd. Daarom dient reisorkestatie alleen te worden gebruikt in gevallen van eenmalig gebruik (individuele gevallen, niet segmenten).

* U moet één actie op het canvas per malplaatje vormen u wenst te gebruiken.

* Wij adviseren dat u een specifieke instantie van het Centrum van het Bericht gebruikt die voor deze integratie wordt ontvangen om het beïnvloeden van andere verrichtingen van Campaign Classic te vermijden die u kunt hebben gaande. De marketingserver kan worden gehost of op locatie worden opgeslagen. De vereiste build is 21.1 Release Candidate.

* Er is geen bevestiging dat de lading of het bericht van de Campaign Classic correct is.

* U kunt geen Campaign Classic-actie gebruiken met een segmentkwalificatie.

## Vereisten

In Campaign Classic, moet u een transactiebericht en zijn bijbehorende gebeurtenis creëren en publiceren. Raadpleeg de [Adobe Campaign Classic-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Neem contact op met Adobe om de JSON-lading op te halen die overeenkomt met elk bericht. U zult dan deze nuttige lading wanneer het vormen van de actie in Journey Orchestration (zie hieronder) kleven.

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

## De handeling configureren

In Journey Orchestration, moet u één actie per transactiebericht vormen. Voer de volgende stappen uit:

1. Maak een nieuwe handeling. Zie deze [sectie](../action/action.md).
1. Voer een naam en beschrijving in.
1. Selecteer **Adobe Campaign Classic** in het veld **Actietype**.
1. Klik in het veld **Payload** en plak een voorbeeld van de JSON-payload die overeenkomt met het Campaign Classic-bericht. Neem contact op met Adobe om deze lading op te halen.
1. Pas de verschillende velden aan. Bepaalde gebieden, zoals kanaalparameters en verpersoonlijkingsgebieden (ctx) moeten als variabelen worden bepaald.
1. Klik **Opslaan**.

![](../assets/accintegration1.png)

Voor elke gevormde actie, is een actieactiviteit beschikbaar in het palet van de reisontwerper.

## Een bericht toevoegen tijdens een reis

1. Ontwerp uw reis, te beginnen met een gebeurtenis. Zie deze [sectie](../building-journeys/journey.md).
1. Selecteer in de sectie **Handeling** van het palet een Campaign Classic-handeling en voeg deze toe aan uw reis.
1. In **Actieparameters**, worden alle gebieden verwacht in de berichtlading getoond. U moet elk van deze gebieden met het gebied in kaart brengen u, of van de gebeurtenis of van de gegevensbron wilt gebruiken. Dit is vergelijkbaar met aangepaste handelingen. Zie deze [sectie](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)

