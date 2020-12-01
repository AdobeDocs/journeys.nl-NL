---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestration-beperkingen
description: Meer informatie over Journey Orchestration-beperkingen
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---


# Beperkingen {#limitations}

Hier zijn beperkingen met betrekking tot het gebruik van Journey Orchestration.

## Algemene actiedrempels

* Er is geen verzendvertraging. 
* In het geval van een fout worden systematisch twee pogingen uitgevoerd. U kunt het aantal pogingen niet aanpassen volgens het ontvangen foutbericht. 
* Met de ingebouwde gebeurtenis **Reaction** kunt u reageren op acties die zich buiten het vak bevinden (zie deze [pagina](../building-journeys/reaction-events.md)). Als u op een bericht wilt reageren dat via een douaneactie wordt verzonden, moet u een specifieke gebeurtenis vormen. 
* Er is geen sprake van een productieve integratie in Adobe Campaign Classic.

## Beperkingen van reisversies {#journey-versions-limitations}

* een reis die begint met een gebeurtenisactiviteit in v1 kan niet met iets anders beginnen dan een gebeurtenis in verdere versies. U kunt geen reis met een gebeurtenis van de Kwalificatie van het **Segment** beginnen.
* een reis die met een activiteit begint van de Kwalificatie **van het** Segment in v1 moet altijd met een Kwalificatie **van het** Segment in verdere versies beginnen.
* Het segment en de naamruimte die zijn gekozen in de **segmentkwalificatie** (eerste knooppunt), kunnen niet worden gewijzigd in nieuwe versies.
* De re-entry regel moet het zelfde in alle reisversies zijn.

## Segmentkwalificatie {#segment-qualification}

* De **de kwalificatieactiviteit** van het Segment kan niet samen met het Transactionele Overseinen van Adobe Campaign Standard wegens productiedruk worden gebruikt. Zie [Adobe Campaign Standard-productbeschrijving](https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html). 
 

## Beperkingen voor aangepaste handelingen

* De URL van de aangepaste handeling ondersteunt geen dynamische parameters. 
* Alleen methoden voor het aanroepen van POSTEN en PUTTEN worden ondersteund. 
* De naam van de queryparameter of -header mag niet beginnen met &quot;.&quot; of &quot;$&quot;. 
* IP-adressen zijn niet toegestaan. 
* Interne Adobe-adressen (.adobe.) zijn niet toegestaan.
 

## Beperkingen Adobe Campaign-acties

* Het Transactionele Overseinen van Adobe Campaign Standard heeft een schaal van 50 000 berichten per uur maximum over kanalen voor een bepaalde instantie. Zie [Adobe Campaign Standard-productbeschrijving](https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html). 
 

## Beperkingen voor gebeurtenissen

* Streaming gegevens die worden gebruikt om een reis van de klant te initiëren, moeten eerst binnen Journey Orchestration worden geconfigureerd om een unieke orchestratie-id te verkrijgen. Deze orkest-id moet worden toegevoegd aan de streaminglading die naar Adobe Experience Platform komt.
 

## Beperkingen op gegevensbronnen

* De externe gegevensbronnen kunnen binnen een klantenreis worden gebruikt om externe gegevens in real time op te zoeken. Deze bronnen moeten bruikbaar zijn via REST API, JSON ondersteunen en het volume van aanvragen kunnen verwerken.