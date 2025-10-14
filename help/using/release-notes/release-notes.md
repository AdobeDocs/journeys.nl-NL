---
product: adobe campaign
title: Aanvullende informatie
description: Meer informatie over opmerkingen bij de release
feature: Journeys
role: User
level: Beginner
exl-id: b923f7e3-997b-483b-b6ac-eef62fc81a84
source-git-commit: 4f6c5f9326b4d1cc4a1a02a036b51e4ad1ae68c4
workflow-type: tm+mt
source-wordcount: '4452'
ht-degree: 35%

---

# Aanvullende informatie {#release-notes}

>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"}  voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._

Deze pagina bevat een overzicht van alle nieuwe functies en verbeteringen voor Journey Orchestration. Voor de eigenschappen van Experience Platform, verwijs naar de volgende [&#x200B; versienota&#39;s &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=nl-NL).

Voor de eigenschappen die na 2022 worden vrijgegeven, de verbindingen direct aan [&#x200B; documentatie van Adobe Journey Optimizer &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} .

## Release van maart 2024 {#mar-rn-2024}

### Verbeteringen {#mar-2024-improvements}

Er zijn nieuwe tussenliggende statussen toegevoegd aan de levenscyclus van de reisontwerpfase:

* **het Publiceren** status tussen de **3&rbrace; status van het Ontwerp &lbrace;en** Levende **status**
* **het Stoppen** status tussen **Levende** status en **beëindigde** status
* **het activeren van testwijze** of **het Deactiveren van testwijze** statussen tussen de **Ontwerp** status en de **(test)** status

Wanneer een reis in een tussenstadium is, is het read-only. [&#x200B; leer meer &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs#filter){target="_blank"} 

## Release van februari 2024 {#feb-rn-2024}

### Verbeteringen {#feb-2024-improvements}

* **filter uw reizen** - u kunt **douanedata nu gebruiken om de reis** inventaris, naast de bestaande vooraf bepaalde datumfilters te filtreren. Op deze manier kunt u de lijst verfijnen door ritten weer te geven die op een bepaalde datum zijn gemaakt of gepubliceerd, binnen een bepaalde maand, gedurende een heel jaar of binnen een opgegeven tijdbereik. [&#x200B; las meer &#x200B;](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=nl-NL#filter){target="_blank"} 
* **de acties van de Douane** - u kunt **inhoud-type** kopbal nu bijwerken. Dit nieuwe **inhoud-type** zou inhoud JSON moeten van verwijzingen voorzien. [&#x200B; las meer &#x200B;](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/about-custom-action-configuration.html?lang=nl-NL#url-configuration){target="_blank"} 
* **Configuratie** - het attribuut identityMap in stepEvents is nu voorgevuld. De primaire identiteit wordt gedefinieerd als &quot;primary = true&quot;. [&#x200B; las meer &#x200B;](https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/reports/sharing-field-list.html?lang=nl-NL){target="_blank"} 
* **Gebruikersinterface** - de hoogste bar, in de transmissieschermen, is gereorganiseerd voor een betere ervaring. Onder de verschillende updates ziet u dat het potlood-pictogram waarmee u de reiseigenschappen kunt openen nu links van de bovenste balk naast de naam van de rit wordt weergegeven. [&#x200B; las meer &#x200B;](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=nl-NL#change-properties){target="_blank"} 

## Release van januari 2024 {#jan-rn-2024}

### Verbeteringen {#jan-2024-improvements}

* **de gebeurtenisduur van de Reactie** - de maximumduur die u in de **gebeurtenissen van de Reactie** kunt bepalen is nu 29 dagen in plaats van 30. [&#x200B; las meer &#x200B;](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/about-journey-building/reaction-events.html?lang=nl-NL){target="_blank"} 
* **Groepen van het Gebied** - Deze versie lost een kwestie op die gebiedsgroepen blokkeerde in bepaalde gevallen worden bewaard.
* Ondersteuning van `<listObject>` is gewijzigd in meerdere functies.

## Release van augustus 2023 {#aug-rn-2023}

### Verbeteringen {#aug-2023-improvements}

* U kunt nu API vraagreacties in douaneacties gebruiken en uw reis structureren die op deze reacties wordt gebaseerd. Deze functie is momenteel beschikbaar als een persoonlijke bètaversie. Verwijs naar de documentatie van Journey Optimizer [&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/action-response.html?lang=nl-NL){target="_blank"} .

## Release van april 2023 {#apr-rn-2023}

### Verbeteringen {#april-2023-improvements}

* De indeling van het configuratievenster, dat wordt weergegeven in handelingen, gegevensbronnen, gebeurtenissen en reizen, is verbeterd.
* U kunt nu statische of dynamische queryparameters definiëren in uw aangepaste handelingen. Verwijs naar de documentatie van Journey Optimizer [&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/about-custom-action-configuration.html?lang=nl-NL#url-configuration){target="_blank"} .
* Nieuwe instructies voor het beheer van de groei van de ervaringen die door de Reizen worden opgedaan:
   * We raden u aan om het aantal knooppunten tot 50 of minder te beperken om uw reizen uitvoerbaar, gemakkelijk te lezen, QA te houden en problemen op te lossen. Het aantal activiteiten wordt weergegeven in de linkerbovensectie van het reiscanvas. Verwijs naar de Journey Optimizer [&#x200B; documentatie &#x200B;](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=nl-NL#journeys-guardrails-journeys){target="_blank"} 
   * Tijdens het ontwikkelen en starten van reizen zullen we u op de hoogte stellen wanneer u de mijlpaal nadert van 100 rechtstreekse reizen in één keer. Als uw plannen meer dan 100 reizen per keer vereisen, gelieve een kaartje voor steun te creëren na het zien van de kennisgeving en wij zullen u helpen. Verwijs naar de Journey Optimizer [&#x200B; documentatie &#x200B;](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=nl-NL#journeys-guardrails-journeys){target="_blank"} 

## Release van maart 2023 {#mar-2023}

### Verbeteringen {#mar-2023-improvements}

* Nieuwe **het Throtteren API** staat u toe om een grens op het aantal gebeurtenissen te plaatsen die per seconde worden verzonden, verhinderend overweldigende verkeerspikes op uw externe systemen of API. Wanneer de ingestelde limiet is bereikt, worden alle volgende API-aanroepen zo snel mogelijk in de wachtrij geplaatst en verwerkt in de volgorde waarin ze zijn ontvangen. Houd er rekening mee dat deze functie slechts ondersteuning biedt voor één configuratie met vertraagde verwerking van al uw sandboxen. [Meer informatie](../api/throttling.md)
* Het canvas Journey is verbeterd voor een eenvoudigere en verbeterde gebruikerservaring. Aan het einde van elk pad op het canvas zijn de lege plaatsaanduidingen verwijderd. U kunt nu gewoon uw activiteiten toevoegen door deze aan het einde van een pad te slepen.
* In het wegcanvas, is het etiket van de **Eind** markering niet meer automatisch plaats met de naam van de vorige activiteit. Gebruikers kunnen desgewenst handmatig een aangepast label toevoegen.
* De standaardonderbreking en foutenduur in reiseigenschappen zijn veranderd van 5 aan 30 seconden. Verwijs naar de documentatie van Journey Optimizer [&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/external-systems/external-systems.html?lang=nl-NL#timeout){target="_blank"} .
* Er is een hulplijn toegevoegd aan de testmodus om alleen te luisteren naar gebeurtenissen die via de interface worden verzonden. Gebeurtenissen die via een extern gereedschap worden verzonden, worden niet in aanmerking genomen. Verwijs naar de documentatie van Journey Optimizer [&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/testing-the-journey.html?lang=nl-NL){target="_blank"} .

## Release van februari 2023 {#feb-2023}

### Verbeteringen {#feb-2023-improvements}

* Het **re-entry wachtt periode** gebied is toegevoegd aan de reiseigenschappen. In dit veld kunt u de tijd definiëren die u moet wachten voordat een profiel de reis weer in één keer kan betreden (te beginnen met een gebeurtenis of een segmentkwalificatie). Hierdoor wordt voorkomen dat ritten meerdere keren ten onrechte worden geactiveerd voor dezelfde gebeurtenis. Het veld wordt standaard ingesteld op 5 minuten. Verwijs naar de documentatie van Journey Optimizer [&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=nl-NL#entrance){target="_blank"} .
* De verbeteringen zijn aangebracht voor **begin en einddata van de reis**. Als u geen begindatum hebt opgegeven, wordt deze nu automatisch toegevoegd op het moment van publicatie. Hiermee kunnen profielen automatisch worden afgesloten wanneer de datum wordt bereikt. Verwijs naar de documentatie van Journey Optimizer [&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=nl-NL#dates){target="_blank"} .

## Release van januari 2023 {#jan-2023-release}

### Verbeteringen {#jan-2023-improvements}

* Wanneer het toevoegen van de kwalificatie van het a **Segment** in een reis, wordt namespace nu pre-gevuld, door gebrek, met laatst gebruikte namespace. Verwijs naar de documentatie van Journey Optimizer [&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/about-journey-building/segment-qualification-events.html?lang=nl-NL#about-segment-qualification){target="_blank"} .
* Op het reiscanvas is er een nieuwe knop beschikbaar op de werkbalk waarmee u een schermafbeelding van uw reis kunt downloaden.

## Release september 2022{#sept-2022-release}

### Nieuwe functies{#sept-2022-features}


<table>
<thead>
<tr>
<th><strong>Beheer en privacy van gegevens</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Met zijn beheerskader voor etikettering en handhaving van gegevensgebruik (DULE) kan Journey Orchestration nu het Adobe Experience Platform-beleid voor governance gebruiken om te voorkomen dat gevoelige velden via aangepaste acties naar systemen van derden worden geëxporteerd. Als het systeem een beperkt veld identificeert in de parameters voor aangepaste handelingen, wordt een fout weergegeven waardoor u de reis niet kunt publiceren.</p>
<p>Het gebruik van de Etikettering en de Handhaving van het Gebruik van Gegevens (DULE) is momenteel beperkt tot geselecteerde klanten, en zal aan alle milieu's in een toekomstige versie worden opgesteld.</p>
<p>Voor meer informatie, verwijs naar de Journey Optimizer <a href="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/action-privacy.html?lang=nl-NL"> documentatie </a>.
</td>
</tr>
</tbody>
</table>

### Verbeteringen{#sept-2022-improvements}

* Er is een nieuwe guardrail toegevoegd aan de unitaire reizen (te beginnen met een evenement of een segmentkwalificatie) om te voorkomen dat ritten meerdere keren ten onrechte voor dezelfde gebeurtenis worden gestart. De terugkeer van het profiel wordt nu tijdelijk geblokkeerd door gebrek voor 5 minuten. Verwijs naar de documentatie van Journey Optimizer [&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=nl-NL#events-g){target="_blank"} .

### Andere wijzigingen{#sept-2022-other}

* Om de prestaties te verbeteren, kunnen de groepen van het de gebeurtenisgebied van de Ervaring niet meer worden gebruikt in reizen die met een de kwalificatieactiviteit van het Segment beginnen. Deze wijziging geldt alleen voor nieuwe reizen. De bestaande zullen het huidige gedrag houden. Verwijs naar de documentatie van Journey Optimizer [&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=nl-NL#expression-editor){target="_blank"} .

### Verbeteringen

* **die een reis** beëindigt - in het wegcanvas, is de **Eind** activiteit verwijderd uit het palet. Eindtags worden nu standaard aan het einde van elk pad toegevoegd en kunnen niet worden verwijderd. Dankzij deze verbetering kan beter worden aangegeven waar een klant de reis heeft verlaten, zonder dat de reisdeskundige enige actie hoeft te ondernemen. Verwijs naar de documentatie van Journey Optimizer [&#128279;](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/end-journey.html?lang=nl-NL){target="_blank"} .

* De **de tijdzone van het Profiel** optie is nu ongecontroleerd door gebrek in reiseigenschappen. [Meer informatie](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/timezone-management.html?lang=nl-NL#timezone-from-profiles){target="_blank"}.

## Release van mei 2022 {#may-2022-release}

### Verbeteringen

* **de redacteur van de Uitdrukking** - de [&#x200B; grens &#x200B;](../functions/functionlimit.md) functie is toegevoegd om u toe te staan om het aantal punten van een lijst te beperken. De [&#x200B; soort &#x200B;](../functions/functionsort.md) functie staat u nu toe om een lijstvoorwerp te sorteren. De steun van listObject is ook toegevoegd aan [&#x200B; disctinct &#x200B;](../functions/functiondistinct.md) en [&#x200B; separatelyWithNull &#x200B;](../functions/functiondistinctwithnull.md) functies.

## Release van maart 2022 {#feb-2022-release}

### Verbeteringen

* Als u wilt voorkomen dat het schema van het uniforme profiel onnodige velden bevat, is het schema voor de gebeurtenis Reisstap niet meer standaard ingeschakeld voor profielen. Indien nodig, kunt u het activeren. [Meer informatie](../building-journeys/sharing-overview.md)
* Journey Optimizer stuurt nu nieuwe stapgebeurtenissen met betrekking tot exporttaken naar Adobe Experience Platform. Voorbeelden van query&#39;s zijn toegevoegd aan documentatie. [Meer informatie](../building-journeys/query-examples.md)

## Release van februari 2022 {#february-2022-release}

### Verbeteringen

* Om prestaties te optimaliseren en verouderd middelgebruik te verhinderen, zullen alle reizen in testwijze die niet voor een week zijn teweeggebracht nu op de status van het Ontwerp terugschakelen. [Meer informatie](../building-journeys/testing-the-journey.md#important_notes)

## Release van januari 2022 {#january-2022-release}

### Verbeteringen

* De de stapgebeurtenissen van Journey Orchestration kunnen nu met andere datasets in [&#x200B; Adobe Customer Journey Analytics &#x200B;](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=nl-NL){target="_blank"} worden verbonden . Het **profileID** gebied, in het ingebouwde schema van de Gebeurtenis van de Stap van de Reis, wordt nu bepaald als identiteitsgebied. [Meer informatie](../building-journeys/sharing-overview.md#integration-cja)
* De begrenzingsregel voor Adobe Campaign Standard-acties is gewijzigd in 4000 oproepen/5 minuten. [Meer informatie](../action/working-with-adobe-campaign.md)

## Release oktober 2021 {#october-2021-release}

### Verbeteringen

* **de redacteur van de Uitdrukking** - als machtsgebruiker, kunt u functies nu gebruiken om met kaarten te werken. [Meer informatie](../expression/field-references.md)
* **Toegankelijkheid** - de verhogingen van de Toegankelijkheid zijn uitgevoerd. Journey Orchestration voldoet nu volledig aan toegankelijkheidsvereisten.
* **Inzamelingen** - de series van voorwerpen die subvoorwerpen bevatten worden nu gesteund. [Meer informatie](../usecase/collections.md)
* **Controle** - De gebeurtenissen van de Stap voor levende reizen en testwijze zijn verbeterd. [&#x200B; de Nieuwe gebieden &#x200B;](../building-journeys/sharing-field-list.md#serviceevents) zijn toegevoegd met betrekking tot de banen van de profieluitvoer. Voor een betere gebruikerservaring zijn de velden voor step-gebeurtenissen nu ingedeeld in verschillende categorieën in het schema voor Journey Step-gebeurtenissen voor Journey Orchestration. Alle vorige gebieden van stapgebeurtenissen zijn nog beschikbaar in de [&#x200B; stepEvents &#x200B;](../building-journeys/sharing-legacy-fields.md) categorie.

## Release september 2021 {#september-2021-release}

<table>
<thead>
<tr>
<th><strong>Gegevenslijsten dynamisch doorgeven met behulp van aangepaste handelingen</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>U kunt nu verzamelingen of een lijst met gegevens in de aangepaste handelingsparameters doorgeven die tijdens runtime dynamisch worden gevuld. Er worden twee soorten verzamelingen ondersteund: eenvoudige verzamelingen en objectverzamelingen. Eerder gemaakte aangepaste handelingen blijven werken. </p>
<p>Voor meer informatie over inzamelingen, verwijs naar de <a href="../usecase/collections.md"> gedetailleerde documentatie </a>. </p>
<p>Het filter en de kruisfuncties zijn toegevoegd aan de lijst met functies die beschikbaar zijn in de geavanceerde expressie-editor. Dit biedt meer mogelijkheden voor het filteren en vergelijken van verzamelingen.</p>
<p>Raadpleeg de documentatie over de <a href="../functions/functionfilter.md"> filter </a> en <a href="../functions/functionintersect.md"> snijdt </a> functies.</p>
</td>
</tr>
</tbody>
</table>

### Verbeteringen

* Systeem produceerde schema&#39;s en datasets die tijdens levering voor stapgebeurtenissen zijn gecreeerd zijn nu op read-only wijze, beschermend tegen om het even welke onbedoelde wijzigingen in kritieke schema&#39;s. [Meer informatie](../building-journeys/sharing-overview.md)
* Cleanly etiketteer **&#x200B;**&#x200B;activiteit met een etiket wachten dat in het canvas zal worden getoond. Het etiket wordt ook gebruikt in rapportering en testwijzelogboeken om duidelijk te identificeren wat u doet. [Meer informatie](../building-journeys/using-the-journey-designer.md)
* Vind uw gebeurtenissen en acties sneller door elementen in de **Gebeurtenissen** en **categorieën van de Actie** te filtreren gebruikend onderzoek. Orchestratie-activiteiten worden niet meer gefilterd. [Meer informatie](../building-journeys/using-the-journey-designer.md)
* Wanneer u een gebeurtenis-id-voorwaarde definieert in een op regels gebaseerde, operator &quot;contains&quot; is nu beschikbaar voor tekenreekstypen velden. [Meer informatie](../event/about-creating.md)

## Release van augustus 2021 {#august-2021-release}

### Verbeteringen

**Reizen**

* **Dynamische kopballen** - u kunt dynamische gegevens in HTTP- kopbalparameters nu overgaan. Deze parameters kunnen door de integratiesystemen worden gebruikt die de vraag van HTTP van de reisactie, bijvoorbeeld timestamp of het volgen identiteitskaart ontvangen. [Meer informatie](../action/url-configuration.md)
* **Dynamische wegen URL** - u kunt de wegen van opstellings dynamische URL voor douaneacties nu. [Meer informatie](../action/url-configuration.md)

## Release van juli 2021 {#july-2021-release}

<table>
<thead>
<tr>
<th><strong>Schema-relaties benutten</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform staat u toe om verhoudingen tussen schema's te bepalen om één dataset als raadplegingslijst voor een andere te gebruiken. Journey Orchestration kan nu gebruikmaken van gegevens die afkomstig zijn van een gekoppeld schema.</p>
<p>Deze gebieden zijn beschikbaar in unitaire gebeurtenisconfiguratie, reisvoorwaarden en douane actieprijsverpersoonlijking.
<p>Raadpleeg de <a href="../event/experience-event-schema.md#leverage_schema_relationships">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

### Verbeteringen

* Het **gebied van de duur van het Geheime voorgeheugen** is verwijderd uit de ruit van de gegevensbronconfiguratie. [Meer informatie](../datasource/about-data-sources.md)

## Release van juni 2021 {#june-2021-release}

<table>
<thead>
<tr>
<th><strong> Adobe Campaign Classic-integratie</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>De integratie met Adobe Campaign Classic is nu GA. Hiermee kunt u e-mails, pushmeldingen en SMS verzenden met de mogelijkheden van Adobe Campaign v7 of v8 Transactieberichten.</p>
<p>De verbinding tussen de Journey Orchestration- en Campagneinstanties wordt door Adobe tijdens de levering ingesteld.</p>
<p>Raadpleeg de <a href="../action/acc-action.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

### Verbeteringen

* Voor externe gegevensbronnen, wordt een het maximum van 15 vraag per seconde nu automatisch bepaald. [Meer informatie](../about/external-systems.md#capping)
* De eenvoudige en geavanceerde expressieeditors ondersteunen nu de XDM-datumindeling.
* In het scherm van de reislijst, is een nieuw filter toegevoegd. U kunt nu filteren op het type transport: **[!UICONTROL Unitary event]** of **[!UICONTROL Segment qualification]** . [Meer informatie](../about/user-interface.md#section_lgm_hpz_pgb)
* Voor live reizen worden in het scherm met de reiseigenschappen nu de publicatiedatum en de naam van de gebruiker weergegeven die de reis heeft gepubliceerd. Deze informatie is ook beschikbaar wanneer u de technische details van de reis kopieert. [Meer informatie](../building-journeys/changing-properties.md#section_lgm_hpz_pgb)

## Release van april 2021 {#april-2021-release}

### Verbeteringen

* In het **scherm van de configuratie van de Gebeurtenis** van de testwijze, wordt een dropdown nu getoond voor gebieden die een opsomming verwachten. Selecteer gewoon een van de beschikbare waarden. Hierdoor worden fouten voorkomen bij het activeren van de gebeurtenis als een onjuiste waarde is gedefinieerd. [Meer informatie](../building-journeys/testing-the-journey.md#firing_events)

## Release van maart 2021 {#march-2021-release}

### Verbeteringen

* Er is een nieuwe status toegevoegd aan de reizen. Wanneer een reis beëindigt of manueel gesloten is, zijn statusschakelaars van **Gesloten** aan **beëindigde** dagen nadat het werd gesloten. Op die manier kunt u inactieve reizen gemakkelijker herkennen en ervoor zorgen dat alle nog aanwezige personen tijd hebben om de reis af te maken. [Meer informatie](../building-journeys/journey.md#ending_a_journey)
* In de activiteitenrechterdeelvensters van conceptreizen zijn alleen-lezen velden nu standaard verborgen. Deze interfacevereenvoudiging zal u helpen uw activiteiten gemakkelijker vormen. Om hen te tonen, klik **read-only gebieden** pictogram tonen, beschikbaar in de hoogste linkerhoek van de ruit van de activiteitenconfiguratie. [Meer informatie](../building-journeys/using-the-journey-designer.md#configuration_pane)
* Op testwijze, op het **scherm van de configuratie van de Gebeurtenis 0&rbrace;**, is het **Zeer belangrijke** gebied dat wordt gebruikt om identiteitskaart van het testprofiel te bepalen hernoemd **hernoemd herkenningsteken van het Profiel** voor een betere gebruikerservaring. [Meer informatie](../building-journeys/testing-the-journey.md).
* Voor reactiegebeurtenissen kan de time-outduur nu alleen worden ingesteld tussen 40 seconden en 30 dagen. Wanneer u een rit test waarbij een reactiegebeurtenis wordt gebruikt, zijn de standaardwaarde voor de testmodus **[!UICONTROL Wait time]** en de minimumwaarde nu 40 seconden. [Meer informatie](../building-journeys/reaction-events.md).

## Release van februari 2021 {#february-2021-release}

<table>
<thead>
<tr>
<th><strong>Profielactiviteit bijwerken</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Met deze nieuwe actieactiviteit kunt u een bestaand Adobe Experience Platform-profiel bijwerken met informatie die afkomstig is van de gebeurtenis, een gegevensbron of een specifieke waarde gebruiken.</p>
<p>Raadpleeg de <a href="../building-journeys/update-profiles.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

### Overige verbeteringen

* Bij het configureren van een gebeurtenis worden nu standaard alleen velden geselecteerd die verplicht zijn voor de XDM-validatie. Deze velden kunnen niet worden uitgeschakeld.
* In het reispalet is een nieuw filter toegevoegd. Hiermee kunt u alleen de laatste vijf gebruikte gebeurtenissen en handelingen weergeven, naast de gebeurtenissen en handelingen die buiten de box vallen. Dit geldt specifiek voor elke gebruiker. Standaard worden alle items weergegeven. [Meer informatie](../building-journeys/using-the-journey-designer.md#palette)
* Bij het starten van een nieuwe rit worden elementen die niet op het canvas kunnen worden neergezet als de eerste stap, nu verborgen. Dit heeft betrekking op alle handelingen, de activiteit van de aandoening, de wachttijd en de reactie.
* In het linkerdeel van de geavanceerde uitdrukkingsredacteur, worden de functies nu opnieuw gegroepeerd onder a **sectie van Functies** aan het eind van de lijst.

## Release van januari 2021 {#january-2021-release}

Wanneer u een schema selecteert in de gebeurtenisconfiguratie, worden alleen velden geselecteerd die verplicht zijn om de gebeurtenis correct te ontvangen door Journey Orchestration. [Meer informatie](../event/defining-the-payload-fields.md)

Eigenschappen voor reizen zijn nu beschikbaar in de eenvoudige expressie-editor. [Meer informatie](../expression/journey-properties.md)

Er zijn twee nieuwe kenmerken voor de reiseigenschappen toegevoegd (sandboxName en organisationId). [Meer informatie](../expression/journey-properties.md)

Om zich aan Adobe Campaign Standard SLAs te richten, wordt een het maximum van 13 vraag per seconde nu automatisch bepaald voor de acties van Adobe Campaign Standard zodra de integratie van Adobe Campaign Standard opstelling is. [Meer informatie](../action/working-with-adobe-campaign.md)

De time-outduur van de gebeurtenis wordt nu duidelijker opgegeven in het time-outpad. [Meer informatie](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)

De [&#x200B; getListItem &#x200B;](../functions/functiongetlistitem.md) en [&#x200B; gespleten &#x200B;](../functions/functionsplit.md) functies zijn toegevoegd aan de lijst van functies beschikbaar in de geavanceerde uitdrukkingsredacteur. Dit zal meer mogelijkheden in uw koordberekeningen gebruiksgevallen aanbieden.

## Release november 2020 {#november-release}

<table>
<thead>
<tr>
<th><strong>Van de ene journey naar de andere gaan</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Met een nieuwe actie kunt u personen van de ene reis naar de andere verplaatsen. De <strong> Jump </strong> activiteit staat u toe:
</p>
<ul>
<li>vereenvoudigen het ontwerp van zeer complexe reizen door deze in verschillende te splitsen </li>
<li>ritten bouwen op basis van gemeenschappelijke en herbruikbare reispatronen</li>
</ul>
<p>Raadpleeg de <a href="../building-journeys/jump.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Eigenschappen voor reizen gebruiken in de expressieeditor</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>In de geavanceerde uitdrukkingsredacteur, hebben wij een nieuwe categorie in de lijst van gebieden en functies toegevoegd. Dit is de informatie die door het systeem wordt opgehaald uit rechtstreekse reizen, zoals de reis-id of de specifieke fouten die zijn aangetroffen. Dit geeft u meer mogelijkheden bij het bouwen van uw reizen. U kunt bijvoorbeeld systemen van derden waarschuwen in het geval van fouten die in een voorwaarde of handeling worden aangetroffen.
</p>
<p>Raadpleeg de <a href="../expression/journey-properties.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Op regels gebaseerde gebeurtenissen (bèta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Een nieuwe methode is nu beschikbaar om uw gebeurtenissen gemakkelijker in te stellen, zonder een eventID te gebruiken: op regel gebaseerde gebeurtenissen evalueren of de gebeurtenis volgens een voorwaarde moet worden geactiveerd. U kunt nog steeds de bestaande methode gebruiken, die nu "door het systeem gegenereerd" wordt genoemd. Deze functie, die is getest door een beperkt aantal klanten via het Alpha-programma, is nu beschikbaar in Beta voor alle klanten.
</p>
</td>
</tr>
</tbody>
</table>

### Overige verbeteringen

Er zijn beperkingen toegevoegd bij het maken van nieuwe versies van een reis. Deze beperkingen voorkomen te drastische veranderingen in de reis om enige consistentie tussen versies te behouden. [Meer informatie](../about/limitations.md#journey-versions-limitations)

De **activiteit van de Kwalificatie van het 1&rbrace; Segment** kan niet meer in een reis worden gebruikt die het berichtactiviteiten van Campaign Standard omvat. Deze beperking beschermt de integriteit van Adobe Campaign Standard-instanties. Het gebruik van de Kwalificatie van Segment kan zelfs tot dagelijkse pieken van bericht leiden die Campaign Standard Transactional Messaging zou overbelasten. [Meer informatie](../about/limitations.md#segment-qualification)

## Release oktober 2020 {#october-release}

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

### Overige verbeteringen

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

### Alpha-updates{#september-alpha-update}

<table>
<thead>
<tr>
<th><strong>Verbeteringen voor segmentactiviteit lezen</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>De volgende verbeteringen zijn aangebracht aan de <strong> Gelezen segment </strong> activiteit:
</p>
<ul>
<li><p>Op segmenten gebaseerde reizen tonen nu, boven het canvas, een herinnering aan het planningstype van de reis. U kunt op deze herinnering klikken om tot het menu van de planningsconfiguratie toegang te hebben.</p>
</li>
<li><p>De granulariteit van de logboeken van de testwijze is verbeterd om de de vooruitgangsstatus van de segmentuitvoer te tonen.</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Release van augustus 2020 {#august-release}

### GA-updates{#august-ga-update}

De payload van segmentkwalificatiegebeurtenissen bevat nu de volgende contextinformatie, die u in voorwaarden en acties kunt gebruiken: het gedrag (openen, sluiten), het tijdstempel van kwalificatie en de segment-ID. [Meer informatie](../building-journeys/segment-qualification-events.md)

### Alpha-updates{#august-alpha-update}

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
<li><p>De configuratie van de reisplanner is verwijderd uit de eigenschappen van de activiteit. De activiteit is nu direct toegankelijk vanuit de eigenschappen van de journey in een specifieke sectie die wordt weergegeven als een activiteit voor Segment lezen op het canvas is neergezet. </p>
</li>
<li><p>U kunt de journey nu testen op een uniform profiel en de voortgang van de journey volgen met behulp van de visuele stroom.</p>
</li>
</ul>
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
<li><p>U kunt nu alle Adobe Analytics-gedragsgebeurtenisgegevens die u al vastlegt en naar het platform streamt, gebruiken om journey’s te starten en ervaringen voor uw klanten te automatiseren. <a href="../event/about-analytics.md">Meer informatie</a></p>
</li>
<li><p>Wanneer u een op regels gebaseerde gebeurtenis activeert in de testmodus, kunt u de voorwaarde van de gebeurtenis-ID nu rechtstreeks weergeven. Ook is er een tooltip toegevoegd naast elk veld dat deel uitmaakt van de regelevaluatie. <a href="../building-journeys/testing-the-journey.md#test-rule-based">Meer informatie</a></p>
</li>
<li><p>Het scherm voor de definitie van op regels gebaseerde gebeurtenissen is gereorganiseerd voor een betere ervaring. <a href="../event/about-creating.md">Meer informatie</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Alpha Release - juli 2020 {#alpha-release---july-2020}

Het Alfa-programma biedt functies die momenteel bij een beperkt aantal klanten worden getest. Hierdoor kunnen we ons product verbeteren op basis van de ontvangen feedback. Deze functies zijn niet beschikbaar voor alle Journey Orchestration-klanten.

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
<p>Met de segmenttriggeractiviteit kunt u alle personen die tot een Adobe Experience Platform-segment behoren, een journey laten starten. Het betreden van een reis kan één keer of op regelmatige basis plaatsvinden. 
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
<p>We hebben de manier vereenvoudigd waarop u Experience-gebeurtenissen instelt. We introduceren een nieuwe methode waarvoor geen eventID nodig is. Wanneer u de gebeurtenis instelt in Journey Orchestration, kunt u nu een op regels gebaseerde gebeurtenis definiëren. <a href="../event/about-events.md">Meer informatie</a>
</p>
</td>
</tr>
</tbody>
</table>


## Release Q2 - juni 2020 {#q2-release---june-2020}

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
<li><p>De segmenten van Adobe Experience Platform kunnen nu worden gecreeerd en worden uitgegeven zonder de interface van Journey Orchestration te verlaten, dankzij een nieuwe <strong> Segmenten </strong> tabel. <a href="../segment/about-segments.md">Meer informatie</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>In de eenvoudige uitdrukkingsredacteur, zijn de segmenten van Adobe Experience Platform nu direct vermeld in de navigatieboom om gemakkelijke opstelling van voorwaarden zoals "toe te staan behoort deze persoon tot segment A?". <a href="../segment/using-a-segment.md">Meer informatie</a></p>
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

## Release Q1 - maart 2020 {#q1-release---march-2020}

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
