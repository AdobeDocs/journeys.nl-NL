---
product: adobe campaign
title: Overzicht van het delen van journeystappen
description: Overzicht van het delen van journeystappen
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 4f6c5f9326b4d1cc4a1a02a036b51e4ad1ae68c4
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 3%

---

# Overzicht van het delen van journeystappen{#sharing-overview}

[!DNL Journey Orchestration] stuurt automatisch gegevens over de reisprestaties naar de Adobe Experience Platform, zodat deze kunnen worden gecombineerd met andere gegevens voor analysedoeleinden.

>[!NOTE]
>
>Deze functie wordt standaard geactiveerd bij alle gebeurtenissen voor stappen tijdens de reis. U kunt niet de schema&#39;s en datasets wijzigen of bijwerken die tijdens levering voor step gebeurtenissen zijn gecreeerd. Door gebrek, zijn deze schema&#39;s en datasets op read-only wijze.

U hebt bijvoorbeeld een reis ingesteld die meerdere e-mails verzendt. Met deze functie kunt u [!DNL Journey Orchestration] -gegevens combineren met gegevens over gebeurtenissen stroomafwaarts, zoals hoeveel conversies er hebben plaatsgevonden, hoeveel betrokkenheid er op de website heeft plaatsgevonden of hoeveel transacties er in de winkel hebben plaatsgevonden. De reisinformatie kan worden gecombineerd met gegevens over de Adobe Experience Platform, hetzij uit andere digitale eigenschappen, hetzij uit offline eigenschappen, om een uitgebreider beeld van de prestaties te krijgen.

[!DNL Journey Orchestration] leidt automatisch tot de noodzakelijke schema&#39;s en stromen in datasets aan Adobe Experience Platform voor elke stap een individu neemt een reis. Een step-gebeurtenis komt overeen met een individuele gebeurtenis die zich tijdens een rit van het ene knooppunt naar het andere verplaatst. Bijvoorbeeld, in een reis die een gebeurtenis, een voorwaarde en een actie heeft, worden de drie stapgebeurtenissen verzonden naar Adobe Experience Platform.

De lijst met XDM-velden die worden doorgegeven, is uitgebreid. Sommige bevatten door het systeem gegenereerde codes en andere hebben door mensen leesbare vriendelijke namen. Voorbeelden zijn het label van de reisactiviteit of de stapstatus: hoe vaak een actie met een time-out of een fout is beëindigd.

>[!CAUTION]
>
>Datasets kunnen niet worden ingeschakeld voor realtime profielservice. Controleer of de schakeloptie **[!UICONTROL Profile]** is uitgeschakeld.

De reizen verzenden gegevens aangezien het voorkomt, op een het stromen manier. U kunt deze gegevens vragen met de Query-service. U kunt verbinding maken met Customer Journey Analytics of andere BI-gereedschappen om gegevens met betrekking tot deze stappen weer te geven.

De volgende schema&#39;s worden gemaakt:

* Gebeurtenisschema voor stap van de reis voor [!DNL Journey Orchestration] - gebeurtenis van de stap van de reis die aan een Meta-gegevens van de Reis wordt gebonden.
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


## Integratie met de Analitycs van de Reis van de Klant{#integration-cja}

De de stapgebeurtenissen van Journey Orchestration kunnen aan andere datasets in [ Adobe Customer Journey Analytics ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) worden verbonden. Hier volgt de algemene workflow:

* Customer Journey Analytics neemt de gegevensset &quot;Journey Step Event&quot; op.
* Het **profileID** gebied in het bijbehorende &quot;schema van de Gebeurtenis van de Stap van de Reis voor Journey Orchestration&quot;wordt bepaald als gebied van de Identiteit. In Customer Journey Analytics, kunt u deze dataset aan een andere dataset dan verbinden die de zelfde waarde zoals persoon gebaseerde herkenningsteken heeft.
* Als u deze dataset in Customer Journey Analytics, voor de analyse van de dwars-kanaalreis zou willen gebruiken, verwijs naar deze [ documentatie ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html).
