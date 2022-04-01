---
product: adobe campaign
title: Overzicht van het delen van journeystappen
description: Overzicht van het delen van journeystappen
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: bb07c0edaae469962ee3bf678664b4a0a83572fe
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 4%

---

# Overzicht van het delen van journeystappen{#sharing-overview}

[!DNL Journey Orchestration] stuurt automatisch gegevens over de reisprestaties naar de Adobe Experience Platform zodat deze kunnen worden gecombineerd met andere gegevens voor analysedoeleinden.

>[!NOTE]
>
>Deze functie wordt standaard geactiveerd bij alle gebeurtenissen voor stappen tijdens de reis. U kunt niet de schema&#39;s en datasets wijzigen of bijwerken die tijdens levering voor step gebeurtenissen zijn gecreeerd. Door gebrek, zijn deze schema&#39;s en datasets op read-only wijze.

U hebt bijvoorbeeld een reis ingesteld die meerdere e-mails verzendt. Dankzij deze functie kunt u [!DNL Journey Orchestration] gegevens met downstreamgebeurtenisgegevens zoals hoeveel conversies hebben plaatsgevonden, hoeveel betrokkenheid op de website heeft plaatsgevonden of hoeveel transacties in de winkel hebben plaatsgevonden. De reisinformatie kan worden gecombineerd met gegevens over de Adobe Experience Platform, hetzij uit andere digitale eigenschappen, hetzij uit offline eigenschappen, om een uitgebreider beeld van de prestaties te krijgen.

[!DNL Journey Orchestration] leidt automatisch tot de noodzakelijke schema&#39;s en stromen in datasets aan de Adobe Experience Platform voor elke stap een individu in een reis neemt. Een step-gebeurtenis komt overeen met een individuele gebeurtenis die zich tijdens een rit van het ene knooppunt naar het andere verplaatst. Bijvoorbeeld, in een reis die een gebeurtenis, een voorwaarde en een actie heeft, worden de drie stapgebeurtenissen verzonden naar Adobe Experience Platform.

De lijst met XDM-velden die worden doorgegeven, is uitgebreid. Sommige bevatten door het systeem gegenereerde codes en andere hebben door mensen leesbare vriendelijke namen. Voorbeelden zijn het etiket van de reisactiviteit of de stapstatus: hoe vaak een time-out of een fout is opgetreden.

>[!CAUTION]
>
>Datasets kunnen niet worden ingeschakeld voor realtime profielservice. Controleer of de **[!UICONTROL Profile]** schakeloptie is uitgeschakeld.

De reizen verzenden gegevens aangezien het voorkomt, op een het stromen manier. U kunt deze gegevens vragen met de Query-service. U kunt verbinding maken met Customer Journey Analytics of andere BI-gereedschappen om gegevens met betrekking tot deze stappen weer te geven.

De volgende schema&#39;s worden gemaakt:

* Dagstapgebeurtenisschema voor [!DNL Journey Orchestration] - Reisstapgebeurtenis die is gekoppeld aan een Reismetagegevens.
* Reisschema met reisvelden voor [!DNL Journey Orchestration] - Reismetagegevens voor het beschrijven van reizen.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

De volgende datasets worden overgegaan:

* Gebeurtenissen reisstap
* Journeys

![](../assets/sharing3.png)

Hier worden de lijsten met XDM-velden weergegeven die aan de Adobe Experience Platform worden doorgegeven:

* [Lijst met gebeurtenisvelden voor stappen](../building-journeys/sharing-field-list.md)
* [Gebeurtenisvelden voor oudere stappen](../building-journeys/sharing-legacy-fields.md)

Kijk hier voor meer informatie over step-gebeurtenissen die aan Adobe Experience Platform worden gerapporteerd [zelfstudievideo](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).

## Integratie met de Analitycs van de Reis van de Klant{#integration-cja}

Journey Orchestration step-gebeurtenissen kunnen worden gekoppeld aan andere datasets in [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html). Hier volgt de algemene workflow:

* Customer Journey Analytics neemt de dataset van de &quot;Gebeurtenis van de Stap van de Reis&quot;op.
* De **profileID** veld in het bijbehorende &quot;Dagboekstapschema voor Journey Orchestration&quot; wordt gedefinieerd als een identiteitsveld. In Customer Journey Analytics, kunt u deze dataset aan een andere dataset dan verbinden die de zelfde waarde zoals persoon gebaseerde herkenningsteken heeft.
* Als u deze dataset in Customer Journey Analytics, voor dwars-kanaalreisanalyse wilt gebruiken, verwijs naar dit [documentatie](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html).
