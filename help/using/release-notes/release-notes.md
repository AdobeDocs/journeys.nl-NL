---
product: adobe campaign
solution: Journey Orchestration
title: Release-opmerkingen
description: Meer informatie over opmerkingen bij de release
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '1731'
ht-degree: 90%

---


# Release-opmerkingen{#release-notes}

Deze pagina bevat een overzicht van alle nieuwe functies en verbeteringen voor Journey Orchestration.
U kunt ook de [Documentatie-updates](../release-notes/documentation-updates.md)raadplegen.

## October 2020 Release {#october-release}

<table>
<thead>
<tr>
<th><strong>Time-out gebeurtenis</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>U kunt nu een time-out voor een gebeurtenis configureren om een reis alleen tijdens een bepaalde tijd naar een gebeurtenis te laten luisteren. U hoeft geen wachtactiviteiten meer parallel aan het gebeurtenispad toe te voegen om dit te bereiken.
</p>
<p>Raadpleeg de <a href="../building-journeys/event-activities.md#listening-to-events-during-a-specific-time">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

### Overige verbeteringen{#october-other}

* Wanneer u een nieuwe versie van een reis publiceert, beëindigt de vorige versie automatisch en schakelt naar de Gesloten status. [Meer informatie](../building-journeys/journey-versions.md)

## Release september 2020 {#september-release}

### GA-updates{#september-ga-update}

<table>
<thead>
<tr>
<th><strong>Verbeteringen in voorwaardenactiviteit</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Wanneer u voorwaarden toevoegt aan uw reis, kunt u nu een etiket bepalen. Als u tijdens een reis verschillende omstandigheden gebruikt, kunt u deze gemakkelijker identificeren.
</p>
<p>Raadpleeg de <a href="../building-journeys/condition-activity.md#about_condition">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

### Alfa-updates{#september-alpha-update}

Raadpleeg deze [sectie](../alpha/alpha-overview.md) om de scope van Alfa te ontdekken.

<table>
<thead>
<tr>
<th><strong>Verbeteringen voor segmentactiviteit lezen</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The following improvements have been made to the <strong>Read segment</strong> activity:
</p>
<ul>
<li><p>Op segmenten gebaseerde reizen tonen nu, boven het canvas, een herinnering aan het planningstype van de reis. U kunt op deze herinnering klikken om tot het menu van de planningsconfiguratie toegang te hebben.</p>
</li>
<li><p>De granulariteit van de logboeken van de testwijze is verbeterd om de de vooruitgangsstatus van de segmentuitvoer te tonen.</p>
</li>
</ul>
<p>Voor meer informatie over de <strong>Gelezen segmentactiviteit</strong> , verwijs naar de <a href="../alpha/alpha-segment-trigger.md">gedetailleerde documentatie</a>.</p>
</td>
</tr>
</tbody>
</table>

## Release van augustus 2020 {#august-release}

### GA-updates{#august-ga-update}

De payload van segmentkwalificatiegebeurtenissen bevat nu de volgende contextinformatie, die u in voorwaarden en acties kunt gebruiken: het gedrag (openen, sluiten), het tijdstempel van kwalificatie en de segment-ID. [Meer informatie](../building-journeys/segment-qualification-events.md)

### Alfa-updates{#august-alpha-update}

Raadpleeg deze [sectie](../alpha/alpha-overview.md) om de scope van Alfa te ontdekken.

<table>
<thead>
<tr>
<th><strong>Segmenttriggeractiviteit</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>De segmenttriggeractiviteit bevat de volgende verbeteringen:
</p>
<ul>
<li><p>De naam van de activiteit is veranderd in ‘Segment lezen’. </p>
</li>
<li><p>De configuratie van de journeyplanner is verwijderd uit de eigenschappen van de activiteit. De activiteit is nu direct toegankelijk vanuit de eigenschappen van de journey in een specifieke sectie die wordt weergegeven als een activiteit voor Segment lezen op het canvas is neergezet. </p>
</li>
<li><p>U kunt de journey nu testen op een uniform profiel en de voortgang van de journey volgen met behulp van de visuele stroom.</p>
</li>
</ul>
<p>Raadpleeg de <a href="../alpha/alpha-segment-trigger.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Gebeurtenissen op basis van regels</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>De volgende verbeteringen zijn doorgevoerd in op regels gebaseerde gebeurtenissen:
</p>
<ul>
<li><p>U kunt nu alle Adobe Analytics-gedragsgebeurtenisgegevens die u al vastlegt en naar het platform streamt, gebruiken om journey’s te starten en ervaringen voor uw klanten te automatiseren. <a href="../alpha/alpha-events.md#analytics-data">Meer informatie</a></p>
</li>
<li><p>Wanneer u een op regels gebaseerde gebeurtenis activeert in de testmodus, kunt u de voorwaarde van de gebeurtenis-ID nu rechtstreeks weergeven. Ook is er een tooltip toegevoegd naast elk veld dat deel uitmaakt van de regelevaluatie. <a href="../alpha/alpha-events.md#configuring-rule-based">Meer informatie</a></p>
</li>
<li><p>Het scherm voor de definitie van op regels gebaseerde gebeurtenissen is gereorganiseerd voor een betere ervaring. <a href="../alpha/alpha-events.md#test-rule-based">Meer informatie</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Alfa-release - juli 2020 {#alpha-release---july-2020}

Het Alfa-programma biedt functies die momenteel bij een beperkt aantal klanten worden getest. Hierdoor kunnen we ons product verbeteren op basis van de ontvangen feedback. Deze functies zijn niet beschikbaar voor alle Journey Orchestration-klanten.

Deze functies worden beschreven in een speciale [sectie](../alpha/alpha-overview.md).

<table>
<thead>
<tr>
<th><strong>Verbeterde gebruikersinterface</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>De navigatie binnen de menu’s van Journey Orchestration is verbeterd en biedt nu een consistente interface met Adobe Experience Platform:
</p>
<ul>
<li><p>Menu’s zijn van de bovenkant verplaatst naar de linkerkant van de interface. </p>
</li>
<li><p>Groepering van beheerdersfuncties in één dashboard.</p>
</li>
</ul>
<p>Raadpleeg de <a href="../alpha/alpha-interface.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Segmenttriggeractiviteit</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Met de segmenttriggeractiviteit kunt u alle personen die tot een Adobe Experience Platform-segment behoren, een journey laten starten. Het starten van een journey kan één keer, of op regelmatige basis plaatsvinden. <a href="../alpha/alpha-segment-trigger.md">Meer informatie</a>
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Gebeurtenissen op basis van regels</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>We hebben de manier vereenvoudigd waarop u Experience-gebeurtenissen instelt. We introduceren een nieuwe methode waarvoor geen eventID nodig is. Wanneer u de gebeurtenis instelt in Journey Orchestration, kunt u nu een op regels gebaseerde gebeurtenis definiëren. <a href="../alpha/alpha-events.md">Meer informatie</a>
</p>
</td>
</tr>
</tbody>
</table>


## Q2-release - juni 2020 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Verbeterde Adobe Experience Platform-integratie</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>De volgende Adobe Experience Platform-integratieverbeteringen zijn doorgevoerd:</p>
<ul>
<li><p>Met een nieuwe activiteit kan worden geluisterd naar het openen en sluiten van Adobe Experience Platform-segmenten waarmee mensen aan een journey beginnen of ermee doorgaan. <a href="../building-journeys/segment-qualification-events.md">Meer informatie</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>U kunt nu Adobe Experience Platform-segmenten maken en bewerken zonder de Journey Orchestration-interface te verlaten dankzij het nieuwe tabblad <strong>Segments. </strong> <a href="../segment/about-segments.md">Meer informatie</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>In de eenvoudige expressie-editor worden Adobe Experience Platform-segmenten nu direct vermeld in de navigatiestructuur voor het gemakkelijk instellen van voorwaarden zoals ‘hoort deze persoon bij segment A?’. <a href="../segment/using-a-segment.md">Meer informatie</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestration geeft nu automatisch de stappen die tijdens journey’s worden uitgevoerd, door aan het Adobe Experience Platform. Dit geldt ook voor mogelijke fouten. Deze informatie kan worden gebruikt voor rapportage en probleemoplossing door query’s uit te voeren op journeystapgebeurtenissen voor een bepaalde journey of voor alle journey’s. <a href="../building-journeys/sharing-overview.md">Meer informatie</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>Journey Orchestration kan nu worden verbonden met productie- en niet-productie Adobe Experience Platform-sandboxen. Sandboxen zijn bètafuncties. <a href="../about/access-management.md#sandboxes">Meer informatie</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Verbeteringen in de journeyontwerper en testmodus</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>De volgende verbeteringen zijn aangebracht aan de journeyontwerper en de testmodus:</p>
<ul>
<li><p>U kunt activiteiten nu kopiëren en plakken van de ene journey naar de andere en 1 of N journeyactiviteiten selecteren. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">Meer informatie</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>Nadat u een gebeurtenis hebt geactiveerd om een testprofiel een journey te laten starten, kunt u nu de voortgang in de journey zien dankzij een gekleurde visuele stroom. In het geval van een fout tijdens de journey worden ook foutdetails weergegeven. <a href="../building-journeys/testing-the-journey.md#firing_events">Meer informatie</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>De <strong>voltooide</strong> journeystatus is hernoemd als <strong>Gesloten (geen toegang)</strong> om beter weer te geven wat deze status betekent.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Overige verbeteringen**

Om te voorkomen dat er te veel API-aanroepen naar externe systemen worden verzonden, is er een nieuwe openbare API voor het instellen van beperkingsregels. Met beperkingsregels kan een maximum aantal aanroepen per milliseconde aan een API-eindpunt worden gedefinieerd. [Meer informatie](../api/capping.md)

Met de toegangscontrole is nu meer granulariteit in het beheer van gebruikerstoegang mogelijk. Beschikbaar: 30 juni 2020. [Meer informatie](../about/access-management.md#create-product-profile)

Journey Orchestration is nu verkrijgbaar in APAC (Australisch datacenter). Beschikbaar: 30 juni 2020

De Journey Orchestration-interface is beschikbaar in het Japans.

## Q1-release - maart 2020 {#q1-release---march-2020}

**Nieuwe functies**

<table>
<thead>
<tr>
<th><strong>Verbeteringen in de testmodus</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>De testmodus is als volgt verbeterd:</p>
<ul>
<li>Wanneer een journey verscheidene gebeurtenissen gebruikt, kunt u elk van deze nu afzonderlijk activeren vanuit een vervolgkeuzelijst in het scherm <strong>Event configuration</strong> van de testmodus. <a href="../building-journeys/testing-the-journey.md#firing_events">Meer informatie</a></p></li>
<li><p>Wanneer een of meer <strong>Wacht</strong>-activiteiten in een journey worden gebruikt, kunt u nu in de testmodus de tijdsduur bepalen voor elk van deze activiteiten. De standaardtijd is 10 seconden. U kunt dit veranderen met de parameter <strong>Wait time in test</strong> linksonder. <a href="../building-journeys/testing-the-journey.md">Meer informatie</a></p><img src="../assets/rn-test.png"/>
</li>
<li>In de <strong>testlogboeken</strong> worden bij een fout tijdens het aanroepen van een extern systeem (databron of actie) nu de foutcode en de reactie op de fout weergegeven. <a href="../building-journeys/testing-the-journey.md#viewing_logs">Meer informatie</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Gecentraliseerd tijdzonebeheer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>Tijdzonebeheer wordt nu centraal geregeld in het deelvenster voor journey-eigenschappen. Er zijn twee parameters toegevoegd aan de journey-eigenschappen:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>In de vervolgkeuzelijst <strong>Timezone</strong> kunt u een specifieke tijdzone selecteren. Standaard wordt de tijdzone van de browser gebruikt. </li>
<li>Met het selectievakje <strong>Profile Timezone</strong> kunt u de Adobe Experience Platform-profieltijdzone gebruiken van de persoon die aan de journey begint, mits beschikbaar. Als dat niet het geval is, wordt de tijdzone gebruikt die in de vervolgkeuzelijst is gedefinieerd. Deze functie is niet compatibel met journey’s die gebeurtenissen gebruiken die geen naamruimte hebben.</li>
</ul>
<p>Raadpleeg de secties <a href="../building-journeys/changing-properties.md#timezone">Eigenschappen wijzigen</a> en <a href="../building-journeys/timezone-management.md">Tijdzonebeheer</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Verbeteringen voor journeyontwerp</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>Het journey<strong>palet</strong> aan de linkerkant van de journeyontwerper is verbeterd:</p>
<ul>
<li>Met een nieuw pictogram naast de <strong>zoekbalk</strong> kunt u niet-beschikbare elementen in het palet verbergen of weergeven, bijvoorbeeld gebeurtenissen die een andere naamruimte gebruiken dan de gebeurtenissen die tijdens de journey worden gebruikt. Niet-beschikbare items zijn standaard verborgen.</li>
<li>Wanneer u het veld <strong>Search</strong> gebruikt, wordt nu het aantal resultaten voor elke categorie canvasactiviteiten weergegeven.</li>
<li>De navigatie tussen de verschillende activiteitencategorieën is verbeterd.</li>
</ul>
<p>In de journeyontwerper kunt u nu controleren of u de meest recente versie van de journey gebruikt. Deze informatie wordt weergegeven naast het versienummer.</p>
<p>Op het journey<strong>canvas</strong> wordt nu een waarschuwingsbericht weergegeven als twee activiteiten worden losgekoppeld.</p>
<img src="../assets/rn-canvas.png"/>
<p>Raadpleeg de <a href="../building-journeys/using-the-journey-designer.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Contextafhankelijke Help</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Er is nu contextafhankelijke Help beschikbaar in de verschillende Journey Orchestration-lijstschermen (journey’s, gebeurtenissen, acties en databronnen). Hiermee kunt u een korte beschrijving weergeven van de huidige functionaliteit en toegang krijgen tot verwante artikelen en video’s.</p>
<p>Klik op het pictogram <img src="../assets/icon-context.png"/> in de rechterbovenhoek van het scherm om de contextafhankelijke Help weer te geven. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Overige verbeteringen**

* Naast de VS is Journey Orchestration nu ook verkrijgbaar in **EMEA**. De applicatie en documentatie zijn in het Frans en Duits beschikbaar.

* Experience League is nu geïntegreerd in het product. Dit vereenvoudigt de toegang tot verwante content en helpt u Experience Cloud optimaal te benutten. Onderaan het tabblad Help hebt u rechtstreeks toegang tot de Journey Orchestration-documentatie. U kunt bovendien op Help > Feedback klikken om problemen te melden of uw ideeën te delen met Adobe.

* De sneltoets **C**, waarmee u een nieuw item kunt maken, is nu beschikbaar in alle lijstschermen: journey’s, databronnen, acties en gebeurtenissen. [Meer informatie](../about/user-interface.md#section_ksq_zr1_ffb)

* U kunt gestopte journey’s nu **verwijderen**. Er zijn geen rapporten beschikbaar over deze verwijderde journey’s.

* Wanneer u door **Adobe Experience Platform-velden** (XDM-indeling) bladert, ziet u nu behalve de veldnaam ook de weergavenaam. Deze informatie wordt opgehaald uit de schemadefinitie in het Gegevenservaringmodel. Indien beschikbaar ziet u de alternatieve weergavenaam. Met deze gebruiksvriendelijke beschrijving, vooral handig bij eVar-velden, kunt u uw velden gemakkelijker identificeren. [Meer informatie](../about/user-interface.md#friendly-names-display)

## GA-release - december 2019 {#ga-release---december-2019}

Journey Orchestration is nu GA.

Stel real-timegebruiksscenario’s voor orkestratie samen aan de hand van contextuele data die zijn opgeslagen in gebeurtenissen of databronnen.

Met Journey Orchestration is real-timeorkestratie mogelijk aan de hand van contextuele data van gebeurtenissen, informatie van het Adobe Experience Platform of data van externe API-services. De applicatie bepaalt in stromen van meerdere stappen die journey’s worden genoemd, de volgende beste acties specifiek voor een bepaalde consument op basis van profiel en gedragingen. Dit omvat zowel de optimale timing als het type actie, zoals het verzenden van een pushbericht aan de consument via de Adobe Campaign Standard-mogelijkheden voor transactionele berichten (Adobe Campaign Standard vereist) of de melding van een extern systeem. Deze beslissingen worden genomen op basis van regels en Sensei-scores.

[Meer informatie](../action/working-with-adobe-campaign.md) over Journey Orchestration.

Aanvullende bronnen:

* [Tutorials](https://docs.adobe.com/content/help/nl-NL/journey-orchestration-learn/tutorials/understanding-journey-orchestration.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)
