---
product: adobe campaign
title: Overzicht van het delen van journeystappen
description: Overzicht van het delen van journeystappen
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 7%

---

# Overzicht van het delen van journeystappen{#sharing-overview}

[!DNL Journey Orchestration] stuurt automatisch gegevens over de reisprestaties naar de Adobe Experience Platform zodat deze kunnen worden gecombineerd met andere gegevens voor analysedoeleinden.

>[!NOTE]
>
>Deze functie wordt standaard geactiveerd bij alle gebeurtenissen voor stappen tijdens de reis. Voor trapsgewijze gebeurtenissen voor het reisprofiel wordt de activering op verzoek uitgevoerd. De schema&#39;s en datasets die tijdens de levering voor deze eigenschap worden gecreeerd moeten niet worden veranderd.

U hebt bijvoorbeeld een reis ingesteld die meerdere e-mails verzendt. Met deze functie kunt u [!DNL Journey Orchestration]-gegevens combineren met gegevens over gebeurtenissen in de downstream, zoals hoeveel conversies er hebben plaatsgevonden, hoeveel betrokkenheid er op de website heeft plaatsgevonden of hoeveel transacties er in de winkel hebben plaatsgevonden. De reisinformatie kan worden gecombineerd met gegevens over de Adobe Experience Platform, hetzij uit andere digitale eigenschappen, hetzij uit offline eigenschappen, om een uitgebreider beeld van de prestaties te krijgen.

[!DNL Journey Orchestration] leidt automatisch tot de noodzakelijke schema&#39;s en stromen in datasets aan de Adobe Experience Platform voor elke stap een individu in een reis neemt. Een step-gebeurtenis komt overeen met een individuele gebeurtenis die zich tijdens een rit van het ene knooppunt naar het andere verplaatst. Bijvoorbeeld, in een reis die een gebeurtenis, een voorwaarde en een actie heeft, worden de drie stapgebeurtenissen verzonden naar Adobe Experience Platform.

De lijst met XDM-velden die worden doorgegeven, is uitgebreid. Sommige bevatten door het systeem gegenereerde codes en andere hebben door mensen leesbare vriendelijke namen. Voorbeelden zijn het etiket van de reisactiviteit of de stapstatus: hoe vaak een time-out of een fout is opgetreden.

>[!CAUTION]
>
>Datasets kunnen niet worden ingeschakeld voor realtime profielservice. Controleer of de schakeloptie **[!UICONTROL Profile]** is uitgeschakeld.

De reizen verzenden gegevens aangezien het voorkomt, op een het stromen manier. U kunt deze gegevens vragen met de Query-service. U kunt verbinding maken met Customer Journey Analytics of andere BI-gereedschappen om gegevens met betrekking tot deze stappen weer te geven.

De volgende schema&#39;s worden gemaakt:

* Gebeurtenissenschema voor trede-stapprofiel voor [!DNL Journey Orchestration] - Ervaar gebeurtenissen voor stappen die in een reis samen met een identiteitskaartje zijn uitgevoerd en die moeten worden gebruikt voor toewijzing aan een individuele deelnemer aan de reis.
* Gebeurtenisschema voor stap van de reis voor [!DNL Journey Orchestration] - gebeurtenis van de stap van de reis die aan een Meta-gegevens van de Reis wordt gebonden.
* Reisschema met reisvelden voor [!DNL Journey Orchestration] - Reismetagegevens om reizen te beschrijven.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

De volgende datasets worden overgegaan:

* Gebeurtenisschema voor stapsgewijze reis voor [!DNL Journey Orchestration]
* Gebeurtenissen reisstap
* Reizen

![](../assets/sharing3.png)

Hier worden de lijsten met XDM-velden weergegeven die aan de Adobe Experience Platform worden doorgegeven:

* [Gemeenschappelijke velden van journeySteps-gebeurtenissen](../building-journeys/sharing-common-fields.md)
* [Velden voor het uitvoeren van acties van journeyStep-gebeurtenissen](../building-journeys/sharing-execution-fields.md)
* [Velden voor het ophalen van gegevens van journeyStep-gebeurtenissen](../building-journeys/sharing-fetch-fields.md)
* [Identiteitsvelden van journeyStep-gebeurtenissen](../building-journeys/sharing-identity-fields.md)
* [journeyvelden](../building-journeys/sharing-journey-fields.md)

Bekijk deze [zelfstudie video](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html) voor meer informatie over stapgebeurtenissen die aan Adobe Experience Platform worden gerapporteerd.
