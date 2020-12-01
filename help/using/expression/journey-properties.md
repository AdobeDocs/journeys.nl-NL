---
product: adobe campaign
solution: Journey Orchestration
title: Reiseigenschappen
description: Meer informatie over reiseigenschappen
translation-type: tm+mt
source-git-commit: 1fd02fcc2a535046cfbcdb5d1c52850ee93370af
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---


# Reiseigenschappen {#journey-properties}

In de geavanceerde uitdrukkingsredacteur, zult u de categorie van Eigenschappen **van de** Reis, onder de gebeurtenis en gegevensbroncategorieën vinden. Deze categorie bevat technische velden die verband houden met de reis voor een bepaald profiel. Dit is de informatie die door het systeem wordt opgehaald uit rechtstreekse reizen, zoals de reis-id of de specifieke fouten die zijn aangetroffen.

![](../assets/journey-properties.png)

U vindt bijvoorbeeld informatie over:

* reisversie: reisuid, reisversie uid, instance uid, enz.
* fouten: gegevens ophalen, handelingen uitvoeren, enz.
* huidige stap, laatste huidige stap enz.
* geneste profielen

U kunt deze velden gebruiken om expressies te maken. Tijdens de uitvoering van de reis worden de waarden direct van de reis opgehaald.

Hier volgen enkele voorbeelden van gebruiksgevallen:

* **Verworpen profielen** in logboek opnemen: u kunt alle profielen verzenden die van een bericht door een het plafonneren regel aan een derdesysteem voor het registreren worden uitgesloten. Hiervoor stelt u een pad in in het geval van een time-out en een fout en voegt u een voorwaarde toe om te filteren op een specifiek fouttype, bijvoorbeeld: &quot;Verwijder mensen door op de regel te tikken&quot;. U kunt de verwijderde profielen vervolgens via een aangepaste handeling naar een systeem van een andere fabrikant duwen.

* **Pushwaarschuwingen verzenden in geval van fouten**: u kunt een bericht naar een derdesysteem verzenden telkens als een fout op een bericht voorkomt. Hiervoor stelt u een pad in bij een fout, voegt u een voorwaarde en een aangepaste handeling toe. U kunt bijvoorbeeld een melding verzenden naar een Slack-kanaal met een beschrijving van de aangetroffen fout.

* **Fouten in rapportage** verfijnen: in plaats van slechts één pad voor foutmeldingen, kunt u een voorwaarde per fouttype definiëren. Hierdoor kunt u de rapportage verfijnen en alle gegevens van fouttypen weergeven.

## Lijst met velden {#journey-properties-fields}

|Categorie|Veldnaam|Label|Beschrijving|
|-|-|-|—|
|Journalisatieversie|reisUID|Reis-id| |
| |tripVersionUID|Journey Version Identifier| |
| |tripVersionName|Journey Version Name| |
| |tripVersionDescription|Journey Version Description| |
| |tripVersion|Journey Version| |
|Journey Instance|instanceUID|Journey Instance Identifier|ID van de instantie|
| |externalKey|External Key|Individuele identificatie die de reis veroorzaakt|
|Identiteit|profielId|Identificatiecode profiel|Identificatiecode van het profiel tijdens de reis|
| |namespace|De Namespace van de Identiteit van het profiel|Namespace van het profiel in de reis (voorbeeld: ECID)|
|Huidig knooppunt|currentNodeId|Huidige knooppuntidentificatie|Id van huidige activiteit (knooppunt)|
| |currentNodeName|CurrentNode Name|Name van de huidige activiteit (knooppunt)|
|Vorige knooppunt|previousNodeId|Previous Node Identifier|Identifier van vorige knooppunt van vorige activiteit (knooppunt)|
| |previousNodeName|Previous Node Name|Name of the previous activity (node)|
|Fouten|lastNodeUIDInError|Last Node Identifier in Error|Identifier of the latest activity (node) in error|
| |lastNodeNameInError|Last Node Name in Error|Name van de laatste activiteit (node) in error|
| |lastNodeTypeInError|Last Node Type in Error|Error type of the latest activity (node) in error. Mogelijke typen:<ul><li>Gebeurtenissen: Gebeurtenissen, Reacties, SQ (voorbeeld: Segmentkwalificatie)</li><li>Stroomregeling: Einde, Voorwaarde, Wacht</li><li>Handelingen: ACS-acties, Springen, Aangepaste actie</li></ul>|
| |lastErrorCode|Last Error Code|Error code of the latest activity (node) in error. Mogelijke fouten: <ul><li>HTTP-foutcodes</li><li>afgetopt</li><li>timedOut</li><li>fout (voorbeeld: standaard in het geval van een onverwachte fout. Dit mag niet of zeer zelden voorkomen.)</li></ul>|
| |lastExecutedActionErrorCode|Laatste uitgevoerde Code van de Fout van de Actie|Foutcode van de recentste actie in fout |
| |lastDataFetchErrorCode|Last Data Fetch Error Code|Foutcode van de meest recente gegevensopname uit gegevensbronnen|
|Tijd|lastActionExecutionElapsedTime|Laatste uitgevoerde actie is verstreken tijd|Tijd besteed aan uitvoering van de nieuwste handeling|
| |lastDataFetchElapsedTime|De laatste gegevens halen verstreken tijd|De tijd die wordt doorgebracht om de recentste gegevens uit gegevensbronnen uit te voeren haalt|
