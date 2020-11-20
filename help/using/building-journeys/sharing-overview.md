---
product: adobe campaign
solution: Journey Orchestration
title: Overzicht van het delen van journeystappen
description: Overzicht van het delen van journeystappen
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 7%

---


# Overzicht van het delen van journeystappen{#sharing-overview}

[!DNL Journey Orchestration] stuurt automatisch gegevens over de reisprestaties naar de Adobe Experience Platform zodat deze kunnen worden gecombineerd met andere gegevens voor analysedoeleinden.

>[!NOTE]
>
>Deze eigenschap wordt niet geactiveerd door gebrek op alle onlangs opgezette instanties. De activering vindt plaats op verzoek.

U hebt bijvoorbeeld een reis ingesteld die meerdere e-mails verzendt. Met deze functie kunt u [!DNL Journey Orchestration] gegevens combineren met gegevens over gebeurtenissen stroomafwaarts, zoals hoeveel conversies er hebben plaatsgevonden, hoeveel betrokkenheid er op de website heeft plaatsgevonden of hoeveel transacties er in de winkel hebben plaatsgevonden. De reisinformatie kan worden gecombineerd met gegevens over de Adobe Experience Platform, hetzij uit andere digitale eigenschappen, hetzij uit offline eigenschappen, om een uitgebreider beeld van de prestaties te krijgen.

[!DNL Journey Orchestration] leidt automatisch tot de noodzakelijke schema&#39;s en stromen in datasets aan de Adobe Experience Platform voor elke stap een individu in een reis neemt. Een step-gebeurtenis komt overeen met een individuele gebeurtenis die zich tijdens een rit van het ene knooppunt naar het andere verplaatst. Bijvoorbeeld, in een reis die een gebeurtenis, een voorwaarde en een actie heeft, worden de drie stapgebeurtenissen verzonden naar Adobe Experience Platform.

De lijst met XDM-velden die worden doorgegeven, is uitgebreid. Sommige bevatten door het systeem gegenereerde codes en andere hebben door mensen leesbare vriendelijke namen. Voorbeelden zijn het etiket van de reisactiviteit of de stapstatus: hoe vaak een time-out of een fout is opgetreden.

>[!CAUTION]
>
>Datasets kunnen niet worden ingeschakeld voor realtime profielservice. Controleer of de **[!UICONTROL Profile]** schakeloptie is uitgeschakeld.

De reizen verzenden gegevens aangezien het voorkomt, op een het stromen manier. U kunt deze gegevens vragen met de Query-service. U kunt verbinding maken met Customer Journey Analytics of andere BI-gereedschappen om gegevens met betrekking tot deze stappen weer te geven.

De volgende schema&#39;s worden gemaakt:

* Het schema van de Gebeurtenis van het Profiel van de Stap van de reis voor - de Gebeurtenissen van de Ervaring voor stappen die in een Reizen samen met een Kaart van de Identiteit worden genomen die voor afbeelding aan een individuele Deelnemer van de Reizen moeten worden gebruikt. [!DNL Journey Orchestration]
* Gebeurtenisschema voor stap van de reis voor [!DNL Journey Orchestration] - gebeurtenis van de stap van de reis die aan een Meta-gegevens van de Reis wordt gebonden.
* Reisschema met reisvelden voor [!DNL Journey Orchestration] - Reismetagegevens voor het beschrijven van reizen.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

De volgende datasets worden overgegaan:

* Gebeurtenisschema voor stapsgewijze reis voor [!DNL Journey Orchestration]
* Gebeurtenissen reisstap
* Reizen

![](../assets/sharing3.png)

Hier worden de lijsten met XDM-velden weergegeven die aan de Adobe Experience Platform worden doorgegeven:

* [journeySteps-gebeurtenissen - gemeenschappelijke velden](../building-journeys/sharing-common-fields.md)
* [journeyStep-gebeurtenissen - velden voor het uitvoeren van acties](../building-journeys/sharing-execution-fields.md)
* [journeyStep-gebeurtenissen - velden voor het ophalen van data](../building-journeys/sharing-fetch-fields.md)
* [journeyStep-gebeurtenissen - identiteitsvelden](../building-journeys/sharing-identity-fields.md)
* [journeyvelden](../building-journeys/sharing-journey-fields.md)

Bekijk deze [zelfstudievideo](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)voor meer informatie over stapgebeurtenissen die aan Adobe Experience Platform worden gerapporteerd.
