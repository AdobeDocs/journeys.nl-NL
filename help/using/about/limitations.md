---
product: adobe campaign
title: Journey Orchestration-beperkingen
description: Meer informatie over Journey Orchestration-beperkingen
feature: Journeys
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 784c91054e0f6b9ea12aa4b7f4079f7c2da8f949
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 2%

---

# Beperkingen {#limitations}

Hier zijn beperkingen met betrekking tot het gebruik van Journey Orchestration.

## Algemene actiedrempels

* Er is geen verzendvertraging. 
* In het geval van een fout worden drie pogingen systematisch opnieuw uitgevoerd. U kunt het aantal pogingen niet aanpassen volgens het ontvangen foutbericht. 
* Met de ingebouwde **Reaction**-gebeurtenis kunt u reageren op acties die buiten de box vallen (zie deze [pagina](../building-journeys/reaction-events.md)). Als u op een bericht wilt reageren dat via een douaneactie wordt verzonden, moet u een specifieke gebeurtenis vormen. 

## Beperkingen van reisversies {#journey-versions-limitations}

* Een reis die begint met een gebeurtenisactiviteit in v1 kan niet met iets anders beginnen dan een gebeurtenis in verdere versies. U kunt geen reis met een **gebeurtenis van de Kwalificatie van het Segment** beginnen.
* Een reis die met een **Kwalificatie van het Segment** activiteit in v1 begint moet altijd met een **Kwalificatie van het Segment** in verdere versies beginnen.
* Het segment en de naamruimte die worden gekozen in **Segmentkwalificatie** (eerste knooppunt) kunnen niet worden gewijzigd in nieuwe versies.
* De re-entry regel moet het zelfde in alle reisversies zijn.

## Segmentkwalificatie {#segment-qualification}

* De **Segmentkwalificatie** activiteit kan niet samen met de Transactionele Overseinen van Adobe Campaign Standard wegens productiebeperkingen worden gebruikt. Zie [Adobe Campaign Standard-productbeschrijving](https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html). 
 

## Beperkingen voor aangepaste handelingen

* De URL van de aangepaste handeling ondersteunt geen dynamische parameters. 
* Alleen methoden voor het aanroepen van POSTEN en PUTTEN worden ondersteund. 
* De naam van de queryparameter of -header mag niet beginnen met &quot;.&quot; of &quot;$&quot;. 
* IP-adressen zijn niet toegestaan. 
* Interne Adobe-adressen (.adobe.) zijn niet toegestaan.
 

## Beperkingen Adobe Campaign-acties

* Het Transactionele Overseinen van Adobe Campaign Standard heeft een schaal van 50 000 berichten per uur maximum over kanalen voor een bepaalde instantie. Zie [Adobe Campaign Standard-productbeschrijving](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Beperkingen voor gebeurtenissen

* Voor door het systeem gegenereerde gebeurtenissen moeten streaming gegevens die worden gebruikt om een klantentraject te starten, eerst binnen Journey Orchestration worden geconfigureerd om een unieke orchestratie-id te verkrijgen. Deze orkest-id moet worden toegevoegd aan de streaminglading die naar Adobe Experience Platform komt. Deze beperking geldt niet voor op regels gebaseerde gebeurtenissen.
 

## Beperkingen op gegevensbronnen

* De externe gegevensbronnen kunnen binnen een klantenreis worden gebruikt om externe gegevens in real time op te zoeken. Deze bronnen moeten bruikbaar zijn via REST API, JSON ondersteunen en het volume van aanvragen kunnen verwerken.

## Reizen die tegelijkertijd met het maken van een profiel beginnen {#journeys-limitation-profile-creation}

Er is een vertraging verbonden aan het maken/bijwerken van een op API gebaseerd profiel in Adobe Experience Platform. Het doel van het Niveau van de Dienst (SLT) in termen van latentie is &lt; 1 min van opname aan Verenigd Profiel voor 95th percentiel van verzoeken, bij een volume van 20K Verzoeken per seconde (RPS).

Als een Reis gelijktijdig aan een profielverwezenlijking wordt teweeggebracht en onmiddellijk controleert/informatie van de Dienst van het Profiel terugwint, zou het niet behoorlijk kunnen werken.

U kunt uit één van deze twee oplossingen kiezen:

* Voeg een wachttijdactiviteit toe na de eerste gebeurtenis om Adobe Experience Platform de tijd te geven die nodig is om de opname naar de profielservice uit te voeren.

* Stel een reis in die niet onmiddellijk gebruikmaakt van het profiel. Als de reis bijvoorbeeld is ontworpen om het maken van een account te bevestigen, kan de ervaringsgebeurtenis informatie bevatten die nodig is om het eerste bevestigingsbericht te verzenden (voornaam, achternaam, e-mailadres, enz.).
