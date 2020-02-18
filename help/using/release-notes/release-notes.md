---
title: Opmerkingen bij de release
description: Meer informatie over opmerkingen bij releases
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
source-git-commit: 8023d7780d43f1de4447c63568f641ce204722c7

---


# Opmerkingen bij de release {#release-notes}

Deze pagina bevat een overzicht van alle nieuwe functies en verbeteringen voor Journey Orchestration.
U kunt ook de [Documentatie-updates](../release-notes/documentation-updates.md)raadplegen.

## Release Q1 - februari 2019 {#q1-release---february-2019}

**Tijdzonebeheer**

Tijdzones worden nu op reisniveau beheerd. Er zijn twee parameters toegevoegd aan de reiseigenschappen:

* Met de vervolgkeuzelijst **Tijdzone** kunt u een specifieke tijdzone selecteren. Standaard wordt de tijdzone van de browser gebruikt.

* Met het selectievakje Tijdzone **van** profiel kunt u de tijdzone van het profiel van het ervaringsplatform gebruiken van de persoon die de reis betreedt, indien beschikbaar. Als niet, zal de timezone in drop-down wordt bepaald worden gebruikt. Deze functie is niet compatibel met reizen zonder naamruimte.

**Contextafhankelijke Help**

Er is nu een contextafhankelijke Help-functie beschikbaar voor de verschillende Journey Orchestration screens. Dit betekent dat u met één klik rechtstreeks toegang hebt tot de documentatie over de functionaliteit die u momenteel gebruikt.

Als u contextafhankelijke Help wilt weergeven, klikt u op het pictogram &#39;i&#39; in de rechterbovenhoek van het scherm.

Deze functie is momenteel beschikbaar in de lijstschermen Home, Gegevensbronnen, Gebeurtenissen en Handelingen.

**Overige wijzigingen**

* In de testmodus kunt u met een nieuwe parameter de tijdspepiner definiëren.  de activiteiten op het gebied van wachttijden kunnen duren . Hierdoor hebt u snel toegang tot de testresultaten.

* In de testmodus kunt u nu alle gebeurtenissen van de rit activeren.


* met een nieuwe parameter kunt u de tijdspepiner definiëren.  de activiteiten op het gebied van wachttijden kunnen duren . Hierdoor hebt u snel toegang tot de testresultaten.

* Reisorchestratie is nu beschikbaar in EMEA.

* Nieuw pictogram in palet om niet-beschikbare items weer te geven of weer te geven. sans namespace. standaard.

* canvas, deconnection, petite icone, qui dit disconnected knooppunt.

* kleine stukjes sigaretten, lijsten

* paletinterface, zoekresultaten met pictogrammen

* Pouvoir capper les call a des APIS externes (data sources or actions). marque n &#39; accept que 500 direct gedetacheerde oproepen , elle pourra mettre un capping a 500 call seconds qui evite de surcharger system de loyalty tiers

* logboeken van het testlogboek. Status avant = fout. quand op toegepaste systemen. Possibilityé de voir code erreur words qu&#39;à renvoyé le systeme. -> ds un test en cas d&#39;erreur, systeme tiers, error code, error response.

* reis stoppen

* reis: versie 1 il de ontmoet is recentste

1er mars.


## GA-release - december 2019 {#ga-release---december-2019}

Reisorchestratie is nu GA.

Stel in real-time implementatiefuncties samen voor het orkestgebruik, waarbij gebruik wordt gemaakt van contextuele gegevens die zijn opgeslagen in gebeurtenissen of gegevensbronnen.

De Orchestratie van de reis staat in real time orchestratie toe die door contextafhankelijke gegevens van gebeurtenissen, informatie van het Platform van de Ervaring van Adobe, of gegevens van de diensten van derdeAPI wordt aangedreven. De toepassing bepaalt in multistep stromen die reizen de volgende beste acties specifiek voor de consument, op hun profiel en gedrag worden genoemd. Dit omvat zowel de optimale timing als het type actie, zoals het verzenden van een pushmelding aan de consument via de mogelijkheden voor transactiemeldingen in Adobe Campagne Standard (hiervoor is Adobe Campagne Standard vereist) of het melden van een systeem van derden. Deze beslissingen worden genomen op basis van regels en Sensei-scores.

[Meer](../action/working-with-adobe-campaign.md) weten over Journey Orchestration?

Aanvullende bronnen:

* [Zelfstudies](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Gemeenschap](https://www.adobe.com/go/journeyorchestrationcommunity)