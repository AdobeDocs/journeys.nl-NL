---
product: adobe campaign
title: Over Campaign Classic-integratie
description: Meer informatie over Campaign Classic-integratie
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 1712529984af02d0a3f678418db1e819370056d6
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---

# Werken met Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Dankzij deze integratie kunt u e-mails, pushberichten en SMS verzenden via de mogelijkheden van Adobe Campaign Classic Transaction Messaging.

De verbinding tussen de instanties van de Journey Orchestration en van de Campaign Classic is opstelling door Adobe bij leveringstijd.

In deze [sectie](../usecase/campaign-classic-use-case.md) wordt een gebruiksgeval van begin tot eind weergegeven.

Voor elke gevormde actie, is een actieactiviteit beschikbaar in het palet van de reisontwerper. Zie deze [sectie](../building-journeys/using-adobe-campaign-classic.md).

## Belangrijke opmerkingen

* Er is geen vertraging van berichten. Wij begrenzen het aantal berichten die over naar 50.000/uur kunnen worden verzonden die op onze huidige Campaign Classic SLA wordt gebaseerd. Daarom dient reisorkestatie alleen te worden gebruikt in gevallen van eenmalig gebruik (individuele gevallen, niet segmenten).

* U moet één actie op het canvas per malplaatje vormen u wenst te gebruiken. U moet één actie in Journey Orchestration voor elke malplaatje vormen u om van Adobe Campaign Classic wenst te gebruiken.

* Wij adviseren dat u een specifieke instantie van het Centrum van het Bericht gebruikt die voor deze integratie wordt ontvangen om het beïnvloeden van andere verrichtingen van Campaign Classic te vermijden die u kunt hebben gaande. De marketingserver kan worden gehost of op locatie worden opgeslagen. De vereiste build is 21.1 Release Candidate of hoger.

* Er is geen bevestiging dat de lading of het bericht van de Campaign Classic correct is.

* U kunt geen Campaign Classic-actie gebruiken met een segmentkwalificatiegebeurtenis.

## Vereisten

In Campaign Classic, moet u een transactiebericht en zijn bijbehorende gebeurtenis creëren en publiceren. Raadpleeg de [Adobe Campaign Classic-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

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

* **kanaal**: het kanaal dat voor uw Campaign Classic transactiemalplaatje wordt bepaald
* **eventType**: de interne naam van de gebeurtenis Campaign Classic
* **ctx**: variabele die op de verpersoonlijking wordt gebaseerd u in uw bericht hebt.

## De handeling configureren

In Journey Orchestration, moet u één actie per transactiebericht vormen. Voer de volgende stappen uit:

1. Maak een nieuwe handeling. Zie deze [sectie](../action/action.md).
1. Voer een naam en beschrijving in.
1. Selecteer **Adobe Campaign Classic** in het veld **Actietype**.
1. Klik in het veld **Payload** en plak een voorbeeld van de JSON-payload die overeenkomt met het Campaign Classic-bericht. Neem contact op met Adobe om deze lading op te halen.
1. Pas de verschillende velden aan op statisch of variabel, afhankelijk van de vraag of u ze wilt toewijzen op het canvas Reis. Bepaalde gebieden, zoals kanaalparameters voor e-mailadres en verpersoonlijkingsgebieden (ctx), wilt u waarschijnlijk bepaald als variabelen voor afbeelding in de context van de reis.
1. Klik **Opslaan**.

![](../assets/accintegration1.png)


