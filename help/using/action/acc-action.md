---
product: adobe campaign
title: Over de integratie van Campagne v7/v8
description: Meer informatie over de integratie van Campagne v7/v8
feature: Journeys
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 5%

---

# Werken met Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}

Deze integratie is beschikbaar voor Adobe Campaign Classic v7 vanaf versie 21.1 en Adobe Campaign v8. Hiermee kunt u e-mails, pushberichten en SMS verzenden met de mogelijkheden van Adobe Campaign Transaction Messaging.

De verbinding tussen de instanties van Journey Orchestration en Campaign wordt door Adobe ingesteld tijdens de inrichting.

In dit hoofdstuk wordt een gebruiksgeval van begin tot eind weergegeven [sectie](../usecase/campaign-classic-use-case.md).

Voor elke gevormde actie, is een actieactiviteit beschikbaar in het palet van de reisontwerper. Zie dit [sectie](../building-journeys/using-adobe-campaign-classic.md).

## Belangrijke opmerkingen

* Er is geen vertraging van berichten. Wij begrenzen het aantal berichten die over aan 50.000/uur kunnen worden verzonden die op onze huidige Campagne SLA wordt gebaseerd. Daarom dient reisorkestatie alleen te worden gebruikt in gevallen van eenmalig gebruik (individuele gevallen, niet segmenten).

* U moet één actie op het canvas per malplaatje vormen u wenst te gebruiken. U moet één actie in Journey Orchestration voor elke malplaatje vormen u om van Adobe Campaign wenst te gebruiken.

* Wij adviseren dat u een specifieke instantie van het Centrum van het Bericht gebruikt die voor deze integratie wordt ontvangen om het beïnvloeden van om het even welke andere verrichtingen van de Campagne te vermijden die u kunt hebben gaande. De marketingserver kan worden gehost of op locatie worden opgeslagen. De vereiste build is 21.1 Release Candidate of hoger.

* Er is geen bevestiging dat de lading of het bericht van de Campagne correct is.

* U kunt geen actie van de Campagne met een gebeurtenis van de segmentkwalificatie gebruiken.

## Vereisten

In Campagne, moet u een transactiebericht en zijn bijbehorende gebeurtenis tot stand brengen en publiceren. Zie de [Adobe Campaign-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

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

## De handeling configureren

In Journey Orchestration, moet u één actie per transactiebericht vormen. Voer de volgende stappen uit:

1. Maak een nieuwe handeling. Zie dit [sectie](../action/action.md).
1. Voer een naam en beschrijving in.
1. In de **Type handeling** veld, selecteren **Adobe Campaign Classic**.
1. Klik in het dialoogvenster **Payload** veld en plak een voorbeeld van de JSON-payload die overeenkomt met het campagnebericht. Neem contact op met Adobe om deze lading op te halen.
1. Pas de verschillende velden aan op statisch of variabel, afhankelijk van de vraag of u ze wilt toewijzen op het canvas Reis. Bepaalde gebieden, zoals kanaalparameters voor e-mailadres en verpersoonlijkingsgebieden (ctx), wilt u waarschijnlijk bepaald als variabelen voor afbeelding in de context van de reis.
1. Klikken **Opslaan**.

![](../assets/accintegration1.png)


