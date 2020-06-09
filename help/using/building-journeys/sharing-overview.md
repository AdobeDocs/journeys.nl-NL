---
title: Overzicht van stap delen voor reizen
description: Overzicht van stap delen voor reizen
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a6a98eca551bf5fc46ebd3a6d0d11486e3fbe06b
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 0%

---


# Overzicht van stap delen voor reizen{#sharing-overview}

Reisorchestratie stuurt automatisch gegevens over de reisprestaties naar de Adobe Experience Platform zodat deze kunnen worden gecombineerd met andere gegevens voor analysedoeleinden.

U hebt bijvoorbeeld een reis ingesteld die meerdere e-mails verzendt. Met deze functie kunt u gegevens van Reisorganisatie combineren met gegevens van downstream-gebeurtenissen, zoals hoeveel conversies er hebben plaatsgevonden, hoeveel betrokkenheid er op de website heeft plaatsgevonden of hoeveel transacties er in de winkel hebben plaatsgevonden. De reisinformatie kan worden gecombineerd met gegevens op het Platform, hetzij van andere digitale eigenschappen of van off-line eigenschappen om een vollediger beeld van prestaties te geven.

De Orchestratie van de reis leidt automatisch tot de noodzakelijke schema&#39;s en stromen in datasets aan het Platform voor elke stap een individu neemt in een reis. Een step-gebeurtenis komt overeen met een individuele gebeurtenis die zich tijdens een rit van het ene knooppunt naar het andere verplaatst. Bijvoorbeeld, in een reis die een gebeurtenis, een voorwaarde en een actie heeft, worden de drie stapgebeurtenissen verzonden naar het Platform.

De lijst met XDM-velden die worden doorgegeven, is uitgebreid. Sommige bevatten door het systeem gegenereerde codes en andere hebben door mensen leesbare vriendelijke namen. Voorbeelden zijn het etiket van de reisactiviteit of de stapstatus: hoe vaak een time-out of een fout is opgetreden.

>[!CAUTION]
>
>Door gebrek, worden de datasets niet aangezet voor de dienst van het tijdprofiel in real time. Als u een dataset in de profieldienst wilt, moet u het (de knevel van het **Profiel** ) aanzetten. Houd er rekening mee dat een groot aantal gebeurtenissen opslagruimte in uw quota in beslag neemt. Ga zorgvuldig te werk voordat u een dataset voor profielen activeert
>
>![](../assets/sharing4.png)

>[!]
>
>De reizen hebben ook de capaciteit of om de gebeurtenis van het Profiel van de Stap van de Reis naar platform al dan niet te verzenden.  Reizen houden een technicus bij om dit te beslissen.
>
>![](../assets/techtoggle.png)

De reizen verzenden gegevens aangezien het voorkomt, op een het stromen manier. U kunt deze gegevens vragen met de Query-service. U kunt verbinding maken met de analysefuncties van de Klant of met andere BI-tools om de gegevens met betrekking tot deze stappen weer te geven.

De volgende schema&#39;s worden gemaakt:

* Het schema van de Gebeurtenis van het Profiel van de Stap van de reis voor Reis Orchestration - de Gebeurtenissen van de Ervaring voor stappen die in een Reis samen met een Kaart van de Identiteit worden genomen die voor afbeelding aan een individuele Deelnemer van de Reis moeten worden gebruikt.
* Gebeurtenisschema voor stap van de reis voor reisorganisatie - gebeurtenis voor stap van de reis die is gekoppeld aan metagegevens van de reis.
* Reisschema met reisvelden voor reisorchestratie - Reismetagegevens voor het beschrijven van reizen.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

De volgende datasets worden overgegaan:

* Tijdlijnstapprofielgebeurtenisschema voor reisorchestratie
* Gebeurtenissen reisstap
* Reizen

![](../assets/sharing3.png)

De lijsten van XDM gebieden die tot het Platform worden overgegaan zijn hier gedetailleerd:

* [tripSteps-gebeurtenissen - gemeenschappelijke velden](../building-journeys/sharing-common-fields.md)
* [uitvoeringsvelden van handelingen voor gebeurtenissen van de tripStep](../building-journeys/sharing-execution-fields.md)
* [gegevens ophalen van gebeurtenissen van de tripStep velden](../building-journeys/sharing-fetch-fields.md)
* [identiteitsvelden van gebeurtenissen van de tripStep](../building-journeys/sharing-identity-fields.md)
* [reisvelden](../building-journeys/sharing-journey-fields.md)

