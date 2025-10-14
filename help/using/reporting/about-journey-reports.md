---
product: adobe campaign
title: Journeyrapporten
description: Leer hoe u uw reisrapporten kunt maken
feature: Journeys
role: User
level: Intermediate
exl-id: 93768321-b171-4338-a440-6ea189a85a4a
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 1%

---

# Journeyrapporten {#concept_rfj_wpt_52b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._



>[!NOTE]
>
>De leveringsgegevens en de component Segmenten worden alleen gevuld als u Adobe Campaign Standard hebt.

In dit gedeelte wordt uitgelegd hoe u rapporten kunt openen en gebruiken om de doeltreffendheid van uw reizen te meten.

## Rapportage-interface {#reporting-interface}

Op de bovenste werkbalk kunt u bijvoorbeeld uw rapport wijzigen, opslaan of afdrukken.

![](../assets/dynamic_report_toolbar.png)

Gebruik de tab **[!UICONTROL Project]** om:

* **[!UICONTROL Open]**: hiermee wordt een eerder gemaakt rapport of sjabloon geopend.
* **[!UICONTROL Save As]**: dupliceert sjablonen om deze te kunnen wijzigen.
* **[!UICONTROL Refresh project]**: werkt uw rapport bij op basis van nieuwe gegevens en wijzigingen in filters.
* **[!UICONTROL Download CSV]** : exporteert uw rapporten naar een CSV-bestand.
* **[!UICONTROL Print]**: drukt uw rapport af.

Op het tabblad **[!UICONTROL Edit]** kunt u het volgende doen:

* **[!UICONTROL Undo]**: hiermee annuleert u de laatste handeling op het dashboard.
* **[!UICONTROL Redo]**: hiermee wordt de laatste **[!UICONTROL Undo]** -actie op het dashboard geannuleerd.
* **[!UICONTROL Clear all]** : verwijdert elk deelvenster op het dashboard.

Met de tabel **[!UICONTROL Insert]** kunt u uw rapporten aanpassen door grafieken en tabellen toe te voegen aan het dashboard:

* **[!UICONTROL New Blank Panel]** : voegt een nieuw leeg deelvenster toe aan het dashboard.
* **[!UICONTROL New Freeform]** : voegt een nieuwe vrije-vormlijst aan uw dashboard toe.
* **[!UICONTROL New Line]** : hiermee voegt u een nieuwe lijngrafiek toe aan het dashboard.
* **[!UICONTROL New Bar]** : hiermee wordt een nieuwe staafgrafiek toegevoegd aan het dashboard.

Met de linkertabbladen kunt u uw rapport samenstellen en de gegevens naar wens filteren.

![](../assets/dynamic_report_interface.png)

Op deze tabbladen hebt u toegang tot de volgende items:

* **[!UICONTROL Panels]**: voeg een leeg paneel of een vrije vorm aan uw rapport toe beginnen uw gegevens te filtreren. Voor meer op dit, verwijs naar [&#x200B; Toevoegend panelen &#x200B;](../reporting/creating-your-journey-reports.md#adding-panels) sectie
* **[!UICONTROL Visualizations]**: sleep en zet een selectie van visualisatie-items neer om uw rapport een grafische dimensie te geven. Voor meer op dit, verwijs naar [&#x200B; het Toevoegen van visualisaties &#x200B;](../reporting/creating-your-journey-reports.md#adding-visualizations) sectie.
* **[!UICONTROL Components]**: pas uw rapporten aan met verschillende afmetingen, metriek, segmenten en tijdsperioden. Voor meer op dit, verwijs naar [&#x200B; Toevoegend componenten &#x200B;](../reporting/creating-your-journey-reports.md#adding-components) sectie.

## Samenvattingssjabloon reis {#ootb-template}

Rapporten zijn verdeeld in twee categorieën: een out-of-the-box sjabloon en aangepaste rapporten.
De out-of-the-box sjabloon, **[!UICONTROL Journey summary]** , geeft u een duidelijke weergave van de belangrijkste volggegevens.

![](../assets/dynamic_report_journey_8.png)

Elke tabel wordt aangegeven met een overzichtsnummer en een overzicht van de diagrammen. U kunt wijzigen hoe de details worden weergegeven in de respectievelijke visualisatie-instellingen.

De volgende KPIs is beschikbaar bij de bovenkant van uw rapport:

* **[!UICONTROL Journey - Entered]**: totaal aantal personen dat de gebeurtenis entry van de reis heeft bereikt.
* **[!UICONTROL Journey - Completion rate]**: het totale aantal personen dat het einde van de reis heeft bereikt (of in het geval van een persoon die niet aan een voorwaarde voldoet) in vergelijking met het totale aantal personen dat de reis heeft betreden.
* **[!UICONTROL Journey - Current]**: totaal aantal personen dat momenteel onderweg is.
* **[!UICONTROL Journey - Failed rate]**: het totale aantal ritten dat niet met succes werd uitgevoerd in vergelijking met het aantal ritten.
* **[!UICONTROL Delivery - Messages sent]**: totaal aantal verzonden berichten.
* **[!UICONTROL Delivery rate]**: het totale aantal berichten dat is afgeleverd in vergelijking met de verzonden berichten.
* **[!UICONTROL Delivery - Bounce rate]**: totaal aantal berichten dat is teruggestuurd in vergelijking met verzonden berichten.
* **[!UICONTROL Delivery - Unsubscribed rate]**: het totale aantal abonnementen door de ontvanger in vergelijking met de geleverde berichten.
* **[!UICONTROL Delivery - Open rate]**: totaal aantal geopende berichten in verhouding tot het aantal geleverde berichten.
* **[!UICONTROL Delivery - Click rate]**: het totale aantal klikken in een levering in verhouding tot het aantal geleverde berichten.

Met de reisvisualisatie kunt u het pad van uw doelprofielen stap voor stap bekijken. Dit is alleen beschikbaar wanneer het gaat om één reis. Deze wordt automatisch gegenereerd en kan niet worden gewijzigd.

![](../assets/dynamic_report_journey_10.png)

De tabel **[!UICONTROL Journey summary]** bevat de gegevens die beschikbaar zijn voor uw reis, zoals:

* **[!UICONTROL Entered]**: totaal aantal personen dat de gebeurtenis entry van de reis heeft bereikt.
* **[!UICONTROL Completion rate]**: het totale aantal personen dat de eindstroommebesturing van de reis heeft bereikt, in vergelijking met het totale aantal personen dat de reis heeft betreden.
* **[!UICONTROL Current]**: totaal aantal personen dat momenteel onderweg is.
* **[!UICONTROL Failed]**: het totale aantal ritten dat niet succesvol is uitgevoerd.
* **[!UICONTROL Failed rate]**: het totale aantal ritten dat niet met succes werd uitgevoerd in vergelijking met het aantal ritten.

In de tabel **[!UICONTROL Top events]** worden de meest geslaagde gebeurtenissen weergegeven en de **[!UICONTROL Top action]** , de meest succesvolle acties tijdens uw reizen.

![](../assets/dynamic_report_journey_11.png)

De tabel **[!UICONTROL Delivery - Sending summary]** bevat de gegevens die beschikbaar zijn voor de levering van uw reis, zoals:

* **[!UICONTROL Processed/sent]**: totaal aantal verzonden berichten.
* **[!UICONTROL Delivered rate]**: het totale aantal berichten dat is afgeleverd in vergelijking met de verzonden berichten.
* **[!UICONTROL Delivered]**: het aantal berichten dat is verzonden in verhouding tot het totale aantal verzonden berichten.
* **[!UICONTROL Bounce + error rate]**: totaal aantal berichten dat is teruggestuurd in vergelijking met verzonden berichten.
* **[!UICONTROL Bounces + errors]**: totaal van fouten die tijdens levering zijn gecumuleerd en automatische retourverwerking in verhouding tot het totale aantal verzonden berichten.

De tabel **[!UICONTROL Delivery - Tracking summary]** bevat de gegevens die beschikbaar zijn om het succes van de leveringen van uw reizen te controleren, zoals:

* **[!UICONTROL Open Rate]**: percentage van geopende berichten.
* **[!UICONTROL Open]**: het aantal keren dat een bericht in een levering werd geopend.
* **[!UICONTROL Click trough rate]**: het totale aantal klikken in een levering in verhouding tot het aantal geleverde berichten.
* **[!UICONTROL Click]**: het aantal keren dat op inhoud is geklikt in een levering.
* **[!UICONTROL Unsubscribe rate]**: percentage van abonnementen door ontvanger in vergelijking met de geleverde berichten.
* **[!UICONTROL Unsubscribed]**: het totale aantal abonnementen door de ontvanger in vergelijking met de geleverde berichten.
