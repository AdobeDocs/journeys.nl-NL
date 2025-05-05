---
product: adobe campaign
title: Journeyeigenschappen
description: Meer informatie over reiseigenschappen
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 0%

---

# Eigenschappen voor reizen {#journey-properties}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


In de geavanceerde uitdrukkingsredacteur, zult u de **categorie van de Eigenschappen van de Reis van 0&rbrace; vinden, onder de gebeurtenis en gegevensbroncategorieën.** Deze categorie bevat technische velden die verband houden met de reis voor een bepaald profiel. Dit is de informatie die door het systeem wordt opgehaald uit rechtstreekse reizen, zoals de reis-id of de specifieke fouten die zijn aangetroffen.

>[!NOTE]
>
>De eigenschappen van de reis zijn ook beschikbaar in de eenvoudige uitdrukkingsredacteur. Zie deze [ sectie ](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

U vindt bijvoorbeeld informatie over:

* reisversie: reisversie uid, reisversie uid, instance uid enz.
* fouten: gegevens ophalen, handelingen uitvoeren, enz.
* huidige stap, laatste huidige stap, enz.
* geneste profielen

U kunt deze velden gebruiken om expressies te maken. Tijdens de uitvoering van de reis worden de waarden direct van de reis opgehaald.

Hier volgen enkele voorbeelden van gebruiksgevallen:

* **Logboek verwierp profielen**: u kunt alle profielen verzenden die van een bericht door een afschilderingsregel aan een derdesysteem voor het registreren doeleinden worden uitgesloten. Hiervoor stelt u een pad in in het geval van een time-out en een fout en voegt u een voorwaarde toe om te filteren op een specifiek fouttype, bijvoorbeeld: &quot;Verwijder mensen door op de regel te tikken&quot;. U kunt de verwijderde profielen vervolgens via een aangepaste handeling naar een systeem van een andere fabrikant duwen.

* **verzendt alarm in het geval van fouten**: u kunt een bericht naar een derdesysteem verzenden telkens als een fout op een bericht voorkomt. Hiervoor stelt u een pad in in het geval van een fout, voegt u een voorwaarde en een aangepaste handeling toe. U kunt bijvoorbeeld een melding verzenden naar een Slack-kanaal met een beschrijving van de aangetroffen fout.

* **verfijnen fouten in het melden**: in plaats van het hebben van enkel één weg voor berichten in fout, kunt u een voorwaarde per foutentype bepalen. Hierdoor kunt u de rapportage verfijnen en alle gegevens van fouttypen weergeven.

## Lijst met velden {#journey-properties-fields}

| Categorie | Veldnaam | Label | Beschrijving |
|---|---|---|------------|
| Reisversie | tripUID | Reis-id | |
| | tripVersionUID | Reisversie-id | |
| | tripVersionName | Naam reisversie | |
| | tripVersionDescription | Beschrijving van reisversie | |
| | tripVersion | Reisversie | |
| Reisexemplaar | instanceUID | Reisexemplaar-id | ID van de instantie |
| | externalKey | Externe sleutel | Individuele identificatie die de reis veroorzaakt |
| | organisationId | Organisatie-id | Merkorganisatie |
| | sandboxName | Naam van sandbox | Naam van de sandbox |
| Identiteit | profileId | Identificatiecode profiel | Identificatiecode van het profiel tijdens de reis |
| | namespace | Naamruimte voor profielidentiteit | Naamruimte van het profiel in de rit (bijvoorbeeld: ECID) |
| Huidig knooppunt | currentNodeId | Huidige knooppunt-id | Identifier van de huidige activiteit (knooppunt) |
| | currentNodeName | Huidige knooppuntnaam | Naam van de huidige activiteit (knooppunt) |
| Vorig knooppunt | previousNodeId | Vorige knooppunt-id | Identifier van de vorige activiteit (knooppunt) |
| | previousNodeName | Vorige knooppunt naam | Naam van de vorige activiteit (knooppunt) |
| Fouten | lastNodeUIDInError | Laatste knooppunt-id in fout | Identifier van de laatste activiteit (knooppunt) in fout |
| | lastNodeNameInError | Laatste knooppuntnaam in fout | Naam van de laatste activiteit (knooppunt) in fout |
| | lastNodeTypeInError | Laatste knooppunttype in fout | Fouttype van de meest recente activiteit (knooppunt) in fout. Mogelijke typen:<ul><li>Gebeurtenissen: gebeurtenissen, reacties, VK (bijvoorbeeld: Segmentkwalificatie)</li><li>Stroombeheer: Einde, Voorwaarde, Wacht</li><li>Handelingen: ACS-handelingen, Springen, Aangepaste handeling</li></ul> |
| | lastErrorCode | Laatste foutcode | Foutcode van de laatste activiteit (knooppunt) in fout. Mogelijke fouten: <ul><li>HTTP-foutcodes</li><li>afgetopt</li><li>timedOut</li><li>fout (voorbeeld: standaard in geval van een onverwachte fout. Dit mag niet of zeer zelden voorkomen.)</li></ul> |
| | lastExecutedActionErrorCode | Foutcode voor laatst uitgevoerde handeling | Foutcode van de laatste foutactie |
| | lastDataFetchErrorCode | Foutcode laatste gegevensophalen | Foutcode van de meest recente gegevensopname van gegevensbronnen |
| Tijd | lastActionExecutionElapsedTime | Uitvoeringstijd laatste handeling verstreken | Tijd besteed aan uitvoering van de laatste handeling |
| | lastDataFetchElapsedTime | Laatste ophalen gegevens verstreken tijd | Tijd besteed aan het uitvoeren van de nieuwste gegevensopname van gegevensbronnen |
