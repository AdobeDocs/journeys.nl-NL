---
product: adobe campaign
title: Journey Orchestration-beperkingen
description: Meer weten over Journey Orchestration-beperkingen?
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---

# Beperkingen {#limitations}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._



Hier zijn beperkingen met betrekking tot het gebruik van Journey Orchestration.

## Algemene reisgeleiders {#journeys-guardrails-journeys}

* Het aantal activiteiten op een reis is beperkt tot 50. Het aantal activiteiten wordt weergegeven in de linkerbovensectie van het reiscanvas.
* Het aantal **levende reizen** in één organisatie is beperkt tot 100 per zandbak. Wanneer deze limiet is bereikt, kunt u geen nieuwe rit meer publiceren.

## Algemene actiedrempels

* In het geval van een fout worden drie pogingen systematisch opnieuw uitgevoerd. U kunt het aantal pogingen niet aanpassen volgens het ontvangen foutbericht. 
* De ingebouwde **gebeurtenis van de Reactie** staat u toe om op uit-van-de-doos acties (zie deze [&#x200B; pagina &#x200B;](../building-journeys/reaction-events.md)) te reageren. Als u op een bericht wilt reageren dat via een douaneactie wordt verzonden, moet u een specifieke gebeurtenis vormen. 

## Beperkingen van reisversies {#journey-versions-limitations}

* Een reis die begint met een gebeurtenisactiviteit in v1 kan niet met iets anders beginnen dan een gebeurtenis in verdere versies. U kunt geen reis met de gebeurtenis van de Kwalificatie van het a **Segment &lbrace;beginnen.**
* Een reis die met de Kwalificatie van het a **Segment** activiteit in v1 begint moet altijd met de Kwalificatie van het a **Segment** in verdere versies beginnen.
* Het segment en namespace die in **kwalificatie van het Segment** (eerste knoop) worden gekozen kunnen niet in nieuwe versies worden veranderd.
* De re-entry regel moet het zelfde in alle reisversies zijn.

## Segmentkwalificatie {#segment-qualification}

* De **kwalificatie van het Segment** activiteit kan niet samen met het Transactionele Overseinen van Adobe Campaign Standard worden gebruikt toe te schrijven aan productiebeperkingen. Zie [&#x200B; Beschrijving van het Product van Adobe Campaign Standard &#x200B;](https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html). 
 

## Beperkingen voor aangepaste handelingen

* De URL van de aangepaste handeling ondersteunt geen dynamische parameters. 
* Alleen aanroepmethoden POST en PUT worden ondersteund. 
* De naam van de queryparameter of -header mag niet beginnen met &quot;.&quot; of &quot;$&quot;. 
* IP-adressen zijn niet toegestaan. 
* Interne Adobe-adressen (.adobe.) zijn niet toegestaan.
 

## Beperkingen Adobe Campaign-acties

* Het Transactionele Overseinen van Adobe Campaign Standard heeft een schaal van 50 000 berichten per uur maximum over kanalen voor een bepaalde instantie. Zie [&#x200B; Beschrijving van het Product van Adobe Campaign Standard &#x200B;](https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html). 
 

## Beperkingen voor gebeurtenissen

* Voor door het systeem gegenereerde gebeurtenissen moeten streaminggegevens die worden gebruikt om een klantentraject te starten, eerst binnen Journey Orchestration worden geconfigureerd om een unieke orchestratie-id te verkrijgen. Deze orkest-id moet worden toegevoegd aan de streaminglading die naar Adobe Experience Platform komt. Deze beperking geldt niet voor op regels gebaseerde gebeurtenissen.
 

## Beperkingen op gegevensbronnen

* De externe gegevensbronnen kunnen binnen een klantenreis worden gebruikt om externe gegevens in real time op te zoeken. Deze bronnen moeten bruikbaar zijn via REST API, JSON ondersteunen en het volume van aanvragen kunnen verwerken.

## Reizen die tegelijkertijd met het maken van een profiel beginnen {#journeys-limitation-profile-creation}

Er is een vertraging verbonden aan het maken/bijwerken van een op API gebaseerd profiel in Adobe Experience Platform. Het doel van het Niveau van de Dienst (SLT) in termen van latentie is &lt; 1 min van opname aan Verenigd Profiel voor 95th percentiel van verzoeken, bij een volume van 20K Verzoeken per seconde (RPS).

Als een Reis gelijktijdig aan een profielverwezenlijking wordt teweeggebracht en onmiddellijk controleert/informatie van de Dienst van het Profiel terugwint, zou het niet behoorlijk kunnen werken.

U kunt uit één van deze twee oplossingen kiezen:

* Voeg een wachttijdactiviteit toe na de eerste gebeurtenis om Adobe Experience Platform de tijd te geven die nodig is om de opname naar de profielservice uit te voeren.

* Stel een reis in die niet onmiddellijk gebruikmaakt van het profiel. Als de reis bijvoorbeeld is ontworpen om het maken van een account te bevestigen, kan de ervaringsgebeurtenis informatie bevatten die nodig is om het eerste bevestigingsbericht te verzenden (voornaam, achternaam, e-mailadres, enz.).
