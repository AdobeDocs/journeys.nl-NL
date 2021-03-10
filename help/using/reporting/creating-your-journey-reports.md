---
product: adobe campaign
solution: Journey Orchestration
title: Journeyrapporten maken
description: Leer hoe u reisrapporten kunt maken
feature: Reizen
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 2%

---


# Journeyrapporten maken {#concept_rfj_wpt_52b}

## Uw rapporten openen en maken {#accessing-reports}

>[!NOTE]
>
>Na het schrappen van een reis, zullen alle bijbehorende rapporten niet meer beschikbaar zijn.

In deze sectie wordt uitgelegd hoe u rapporten kunt maken of gebruiken die zich buiten de box bevinden. Combineer deelvensters, onderdelen en visualisaties om het succes van uw reizen beter te kunnen volgen.

U kunt als volgt de reisrapporten openen en het succes van uw leveringen volgen:

1. Klik in het bovenste menu op het tabblad **[!UICONTROL Home]**.

1. Selecteer de reis u wilt melden.

   U kunt uw rapporten ook openen door op **Rapport** te klikken terwijl u de muis boven een reis in de lijst met reizen houdt.

   ![](../assets/dynamic_report_journey.png)

1. Klik op het pictogram **[!UICONTROL Report]** rechtsboven in het scherm.

   ![](../assets/dynamic_report_journey_2.png)

1. Het **[!UICONTROL Journey summary]** uit-van-de doosrapport verschijnt op het scherm. Klik op de knop **[!UICONTROL Close]** om aangepaste rapporten te openen.

   ![](../assets/dynamic_report_journey_12.png)

1. Klik **[!UICONTROL Create new project]** om uw rapport van kras tot stand te brengen.

   ![](../assets/dynamic_report_journey_3.png)

1. Sleep op het tabblad **[!UICONTROL Panels]** zoveel deelvensters of vrije tabellen als nodig zijn. Zie deze [sectie](#adding-panels) voor meer informatie.

   ![](../assets/dynamic_report_journey_4.png)

1. Vervolgens kunt u uw gegevens filteren door de afmetingen en metriek van het tabblad **[!UICONTROL Components]** naar de vrije-vormtabel te slepen. Zie deze [sectie](#adding-components) voor meer informatie.

   ![](../assets/dynamic_report_journey_5.png)

1. Voor een duidelijkere weergave van uw gegevens kunt u visualisaties toevoegen op het tabblad **[!UICONTROL Visualizations]**. Zie deze [sectie](#adding-visualizations) voor meer informatie.

## Deelvensters toevoegen{#adding-panels}

### Een leeg venster toevoegen {#adding-a-blank-panel}

Om uw rapport te beginnen, kunt u een reeks panelen aan een uit-van-de-doos of douanerapport toevoegen. Elk deelvenster bevat verschillende gegevenssets en bestaat uit vrije-vormtabellen en visualisaties.

In dit deelvenster kunt u uw rapporten naar wens samenstellen. U kunt zoveel deelvensters toevoegen als u wilt in uw rapporten om uw gegevens met verschillende tijdsperiodes te filteren.

1. Klik op het pictogram **[!UICONTROL Panels]**. U kunt ook een deelvenster toevoegen door op **[!UICONTROL Insert tab]** te klikken en **[!UICONTROL New Blank Panel]** te selecteren.

   ![](../assets/dynamic_report_panel_1.png)

1. Sleep de **[!UICONTROL Blank Panel]** naar het dashboard.

   ![](../assets/dynamic_report_panel.png)

U kunt nu een vrije-vormlijst aan uw paneel toevoegen beginnen richtend gegevens.

### Een vrije-vormlijst {#adding-a-freeform-table} toevoegen

Met tabellen met vrije vorm kunt u een tabel maken om uw gegevens te analyseren aan de hand van de verschillende waarden en afmetingen die beschikbaar zijn in de tabel **[!UICONTROL Component]**.

Elke lijst en visualisatie is resizable en kan worden bewogen om uw rapport beter aan te passen.

1. Klik op het pictogram **[!UICONTROL Panels]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Sleep het item **[!UICONTROL Freeform]** naar het dashboard.

   U kunt ook een tabel toevoegen door op de tab **[!UICONTROL Insert]** te klikken en **[!UICONTROL New Freeform]** te selecteren of door op **[!UICONTROL Add a freeform table]** in een leeg deelvenster te klikken.

   ![](../assets/dynamic_report_panel_2.png)

1. Sleep items van het tabblad **[!UICONTROL Components]** naar de kolommen en rijen om uw tabel samen te stellen.

   ![](../assets/dynamic_report_freeform_3.png)

1. Klik op het pictogram **[!UICONTROL Settings]** om te wijzigen hoe de gegevens in uw kolommen worden weergegeven.

   ![](../assets/dynamic_report_freeform_4.png)

   De **[!UICONTROL Column settings]** bestaat uit:

   * **[!UICONTROL Number]**: Hiermee kunt u samenvattingsnummers in de kolom tonen of verbergen.
   * **[!UICONTROL Percent]**: Hiermee kunt u percentages in de kolom tonen of verbergen.
   * **[!UICONTROL Interpret zero as no value]**: Hiermee kunt u tonen of verbergen wanneer de waarde gelijk is aan nul.
   * **[!UICONTROL Background]**: Hiermee kunt u de horizontale voortgangsbalk in cellen weergeven of verbergen.
   * **[!UICONTROL Include retries]**: Hiermee kunt u opnieuw proberen opnemen in het resultaat. Dit is alleen beschikbaar voor **[!UICONTROL Sent]** en **[!UICONTROL Bounces + Errors]**.

1. Selecteer een of meerdere rijen en klik op het pictogram **[!UICONTROL Visualize]**. Er wordt een visualisatie toegevoegd die de geselecteerde rijen weerspiegelt.

   ![](../assets/dynamic_report_freeform_5.png)

U kunt nu zo veel componenten toevoegen als u nodig hebt en ook visualisaties toevoegen om grafische representaties van uw gegevens te geven.

## Componenten toevoegen{#adding-components}

Componenten helpen u bij het aanpassen van rapporten met verschillende afmetingen, meetwaarden en tijdsperioden.

1. Klik op het tabblad **[!UICONTROL Components]** om de lijst met componenten te openen.

   ![](../assets/dynamic_report_components.png)

1. In elke categorie op het tabblad **[!UICONTROL Components]** worden de vijf meest gebruikte items weergegeven. Klik op de naam van een categorie voor toegang tot de volledige lijst met componenten.

   De tabel met componenten bestaat uit drie categorieën:

   * **[!UICONTROL Dimensions]**: Krijg details van het leveringslogboek, zoals browser of domein van de ontvanger, of het succes van een levering.
   * **[!UICONTROL Metrics]**: Meer informatie over de status van een bericht. Bijvoorbeeld, als een bericht werd geleverd en de gebruiker het opende.
   * **[!UICONTROL Time]**: Stel een tijdsperiode in voor uw tabel.

1. Sleep componenten in een deelvenster om de gegevens te filteren.

U kunt zoveel componenten slepen en neerzetten als u nodig hebt en deze met elkaar vergelijken.

## Visualisaties toevoegen{#adding-visualizations}

Met het tabblad **[!UICONTROL Visualizations]** kunt u visualisatie-items, zoals gebied, donut en grafiek, slepen en neerzetten. Visualisaties geven u grafische voorstellingen van uw gegevens.

1. Sleep op het tabblad **[!UICONTROL Visualizations]** een visualisatie-item in een deelvenster.

   ![](../assets/dynamic_report_visualization_1.png)

1. Nadat u een visualisatie aan het deelvenster hebt toegevoegd, worden in uw rapporten automatisch de gegevens in uw vrije-vormtabel gedetecteerd. Selecteer de instellingen voor uw visualisatie.
1. Als u meer dan één vrije lijst hebt, kies de beschikbare gegevensbron om in uw grafiek in het **[!UICONTROL Data Source Settings]** venster toe te voegen. Dit venster is ook beschikbaar als u op de gekleurde stip naast de titel voor visualisatie klikt.

   ![](../assets/dynamic_report_visualization_2.png)

1. Klik op de instellingenknop **[!UICONTROL Visualization]** om het grafiektype of de weergave ervan rechtstreeks te wijzigen, zoals:

   * **[!UICONTROL Percentages]**: Hiermee geeft u de waarden weer als een percentage.
   * **[!UICONTROL Anchor Y Axis at Zero]**: Hiermee wordt de y-as naar nul geforceerd, zelfs als de waarden boven nul liggen.
   * **[!UICONTROL Legend visible]**: Hiermee kunt u de legenda verbergen.
   * **[!UICONTROL Normalization]**: Hiermee past u waarden aan.
   * **[!UICONTROL Display Dual Axis]**: Hiermee voegt u een andere as aan de grafiek toe.
   * **[!UICONTROL Limit Max Items]**: Hiermee beperkt u het aantal weergegeven grafieken.
   * **[!UICONTROL Threshold]**: Hiermee kunt u een drempelwaarde instellen voor uw grafiek. Het wordt weergegeven als een zwarte stippellijn.

   ![](../assets/dynamic_report_visualization_3.png)

Dankzij deze visualisatie hebt u een duidelijker beeld van uw gegevens in uw rapporten.