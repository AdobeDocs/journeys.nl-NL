---
product: adobe campaign
title: Over de integratie van Campagne v7/v8
description: Meer informatie over de integratie van Campagne v7/v8
feature: Journeys
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 1%

---

# Werken met Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Deze integratie is beschikbaar voor Adobe Campaign Classic v7 vanaf versie 21.1 en Adobe Campaign v8. Hiermee kunt u e-mails, pushberichten en SMS verzenden met de mogelijkheden van Adobe Campaign Transaction Messaging.

De verbinding tussen de Journey Orchestration- en Campagneinstanties wordt door Adobe tijdens de levering ingesteld.

Een gebruiksgeval van begin tot eind wordt voorgesteld in deze [ sectie ](../usecase/campaign-classic-use-case.md).

Voor elke gevormde actie, is een actieactiviteit beschikbaar in het palet van de reisontwerper. Verwijs naar deze [ sectie ](../building-journeys/using-adobe-campaign-classic.md).

## Belangrijke opmerkingen

* Er is geen vertraging van berichten. We beperken het aantal berichten dat meer dan 50.000 per uur kan worden verzonden op basis van onze huidige campagne-SLA. Daarom dient reisorkestatie alleen te worden gebruikt in gevallen van eenmalig gebruik (individuele gevallen, niet segmenten).

* U moet één actie op het canvas per malplaatje vormen u wenst te gebruiken. U moet één actie in Journey Orchestration voor elke malplaatje vormen u om van Adobe Campaign wenst te gebruiken.

* Wij adviseren dat u een specifieke instantie van het Centrum van het Bericht gebruikt die voor deze integratie wordt ontvangen om het beïnvloeden van om het even welke andere verrichtingen van de Campagne te vermijden die u kunt hebben gaande. De marketingserver kan worden gehost of op locatie worden opgeslagen. De vereiste build is 21.1 Release Candidate of hoger.

* Er is geen bevestiging dat de lading of het bericht van de Campagne correct is.

* U kunt geen actie van de Campagne met een gebeurtenis van de segmentkwalificatie gebruiken.

## Vereisten

In Campagne, moet u een transactiebericht en zijn bijbehorende gebeurtenis tot stand brengen en publiceren. Verwijs naar de [ documentatie van Adobe Campaign ](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=nl-NL#transactional-messaging).

U kunt uw JSON-lading voor elk bericht samenstellen volgens het onderstaande patroon. U gaat deze payload vervolgens plakken tijdens het configureren van de handeling in Journey Orchestration (zie hieronder)

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

* **kanaal**: het kanaal dat voor uw het transactiemalplaatje van de Campagne wordt bepaald
* **eventType**: de interne naam van uw gebeurtenis van de Campagne
* **ctx**: variabele die op de personalisatie wordt gebaseerd u in uw bericht hebt.

## De handeling configureren

In Journey Orchestration moet u één actie per transactiemelding configureren. Voer de volgende stappen uit:

1. Maak een nieuwe handeling. Verwijs naar deze [ sectie ](../action/action.md).
1. Voer een naam en beschrijving in.
1. Op het **type van Actie** gebied, uitgezochte **Adobe Campaign Classic**.
1. Klik op het **gebied van de Lading** en kleef een voorbeeld van JSON nuttige lading die aan het bericht van de Campagne beantwoordt. Neem contact op met Adobe voor deze lading.
1. Pas de verschillende velden aan op statisch of variabel, afhankelijk van de vraag of u ze wilt toewijzen op het canvas Reis. Bepaalde gebieden, zoals kanaalparameters voor e-mailadres en verpersoonlijkingsgebieden (ctx), wilt u waarschijnlijk bepaald als variabelen voor afbeelding in de context van de reis.
1. Klik **sparen**.

![](../assets/accintegration1.png)


