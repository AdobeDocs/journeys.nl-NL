---
product: adobe campaign
title: Overzicht van het delen van journeystappen
description: Overzicht van het delen van journeystappen
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: b557e94076bc7ce5c212246ddf313248ca10dd60
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 2%

---

# Overzicht van het delen van journeystappen{#sharing-overview}

[!DNL Journey Orchestration] stuurt automatisch gegevens over de reisprestaties naar de Adobe Experience Platform zodat deze kunnen worden gecombineerd met andere gegevens voor analysedoeleinden.

>[!NOTE]
>
>Deze functie wordt standaard geactiveerd bij alle gebeurtenissen voor stappen tijdens de reis. Voor trapsgewijze gebeurtenissen voor het reisprofiel wordt de activering op verzoek uitgevoerd. U kunt niet de schema&#39;s en datasets wijzigen of bijwerken die tijdens levering voor step gebeurtenissen zijn gecreeerd. Door gebrek, zijn deze schema&#39;s en datasets op read-only wijze.

U hebt bijvoorbeeld een reis ingesteld die meerdere e-mails verzendt. Dankzij deze functie kunt u [!DNL Journey Orchestration] gegevens met downstreamgebeurtenisgegevens zoals hoeveel conversies hebben plaatsgevonden, hoeveel betrokkenheid op de website heeft plaatsgevonden of hoeveel transacties in de winkel hebben plaatsgevonden. De reisinformatie kan worden gecombineerd met gegevens over de Adobe Experience Platform, hetzij uit andere digitale eigenschappen, hetzij uit offline eigenschappen, om een uitgebreider beeld van de prestaties te krijgen.

[!DNL Journey Orchestration] leidt automatisch tot de noodzakelijke schema&#39;s en stromen in datasets aan de Adobe Experience Platform voor elke stap een individu in een reis neemt. Een step-gebeurtenis komt overeen met een individuele gebeurtenis die zich tijdens een rit van het ene knooppunt naar het andere verplaatst. Bijvoorbeeld, in een reis die een gebeurtenis, een voorwaarde en een actie heeft, worden de drie stapgebeurtenissen verzonden naar Adobe Experience Platform.

De lijst met XDM-velden die worden doorgegeven, is uitgebreid. Sommige bevatten door het systeem gegenereerde codes en andere hebben door mensen leesbare vriendelijke namen. Voorbeelden zijn het etiket van de reisactiviteit of de stapstatus: hoe vaak een time-out of een fout is opgetreden.

>[!CAUTION]
>
>Datasets kunnen niet worden ingeschakeld voor realtime profielservice. Controleer of de **[!UICONTROL Profile]** schakeloptie is uitgeschakeld.

De reizen verzenden gegevens aangezien het voorkomt, op een het stromen manier. U kunt deze gegevens vragen met de Query-service. U kunt verbinding maken met Customer Journey Analytics of andere BI-gereedschappen om gegevens met betrekking tot deze stappen weer te geven.

De volgende schema&#39;s worden gemaakt:

* Gebeurtenisschema voor stapsgewijze reis voor [!DNL Journey Orchestration] - Ervaar gebeurtenissen voor stappen die in een reis samen met een Identiteitskaart worden genomen om aan een individuele deelnemer van de Reis in kaart te brengen.
* Dagstapgebeurtenisschema voor [!DNL Journey Orchestration] - Reisstapgebeurtenis die is gekoppeld aan een Reismetagegevens.
* Reisschema met reisvelden voor [!DNL Journey Orchestration] - Reismetagegevens voor het beschrijven van reizen.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

De volgende datasets worden overgegaan:

* Gebeurtenisschema voor stapsgewijze reis voor [!DNL Journey Orchestration]
* Gebeurtenissen reisstap
* Journeys

![](../assets/sharing3.png)

Hier worden de lijsten met XDM-velden weergegeven die aan de Adobe Experience Platform worden doorgegeven:

* [Lijst met gebeurtenisvelden](../building-journeys/sharing-field-list.md)
* [Gebeurtenisvelden voor oudere stappen](../building-journeys/sharing-legacy-fields.md)

Kijk hier voor meer informatie over step-gebeurtenissen die aan Adobe Experience Platform worden gerapporteerd [zelfstudievideo](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).
