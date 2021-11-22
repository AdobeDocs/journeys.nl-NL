---
product: adobe campaign
title: De gebruikersinterface
description: Meer informatie over de gebruikersinterface
feature: Journeys
role: User
level: Intermediate
exl-id: 0d0e74c7-6cb0-4068-a69a-3c01f8b3552d
source-git-commit: a5ec1c4c5608113bb17dfbdea0587f6bb342099a
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 61%

---

# Gebruikersinterface{#concept_rcq_lqt_52b}

>[!NOTE]
>
>We raden u aan Chrome als uw internetbrowser te gebruiken om het beste uit [!DNL Journey Orchestration] te halen. De interface wordt weergegeven in de taal die is gedefinieerd in IMS. Als uw IMS-taal niet door [!DNL Journey Orchestration] wordt ondersteund, wordt de interface weergegeven in het Engels.
>
>Deze documentatie wordt regelmatig aangepast aan recente wijzigingen in het product. Sommige screenshots kunnen echter iets afwijken van de interface van het product.

## Toegang tot [!DNL Journey Orchestration]{#accessing_journey_orchestration}

Om toegang te krijgen tot [!DNL Journey Orchestration]s interface, klik **[!UICONTROL App Selector]** in de rechterbovenhoek, en klik vervolgens op **[!UICONTROL Journey Orchestration]**.

![](../assets/journey1.png)

U kunt [!DNL Journey Orchestration] ook openen via de startpagina van Experience Cloud, in de sectie **[!UICONTROL Quick access]**.

![](../assets/journey1bis.png)

## De interface verkennen{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="Journeylijst"
>abstract="Met de journeylijst kunt u al uw journey’s tegelijk weergeven, hun status bekijken en basisacties uitvoeren."
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="Demovideo bekijken"

Met de bovenste menu’s kunt u navigeren door de verschillende functies van [!DNL Journey Orchestration]: **[!UICONTROL Home]** (de journey’s), **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** en **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Klik op het pictogram ![](../assets/icon-context.png) in de rechterbovenhoek van het scherm om de contextafhankelijke Help weer te geven. Deze is beschikbaar in de verschillende [!DNL Journey Orchestration]-lijstschermen (journey’s, gebeurtenissen, acties en databronnen). Hiermee kunt u een korte beschrijving weergeven van de huidige functionaliteit en toegang krijgen tot verwante artikelen en video’s.

![](../assets/journey2bis.png)

## Zoeken en filteren{#section_lgm_hpz_pgb}

In de lijsten **[!UICONTROL Home]**,**[!UICONTROL Data Sources]**, **[!UICONTROL Events]** en **[!UICONTROL Actions]** kunt u met een zoekbalk naar een item zoeken.

U kunt het dialoogvenster **[!UICONTROL Filters]** openen door te klikken op het filterpictogram linksboven van de lijst. Met het menu Filters kunt u de weergegeven elementen filteren op basis van verschillende criteria. U kunt ervoor kiezen alleen de elementen van een bepaald type of een bepaalde status weer te geven, de elementen die u hebt gemaakt, of de elementen die in de afgelopen 30 dagen zijn gewijzigd.

Gebruik in de lijsten **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** en **[!UICONTROL Actions]** de **[!UICONTROL Creation filters]** om te filteren op de datum waarop en de gebruiker door wie een element is gemaakt. U kunt bijvoorbeeld besluiten alleen gebeurtenissen weer te geven die u in de afgelopen 30 dagen hebt gemaakt.

In de reislijst (onder **[!UICONTROL Home]**, naast de **[!UICONTROL Creation filters]** kunt u de weergegeven reizen ook filteren op basis van hun status, type en versie (**[!UICONTROL Status and version filters]**). Het type kan zijn: **[!UICONTROL Unitary event]** of **[!UICONTROL Segment qualification]**. U kunt er ook voor kiezen om alleen de journey’s weer te geven die een bepaalde gebeurtenis, veldengroep of actie (**[!UICONTROL Activity filters]** en **[!UICONTROL Data filters]**) gebruiken. Met **[!UICONTROL Publication filters]** kunt u een publicatiedatum of gebruiker selecteren. U kunt er bijvoorbeeld voor kiezen om alleen de nieuwste versies van live journey’s weer te geven die gisteren zijn gepubliceerd. Zie [deze pagina](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>De weergegeven kolommen kunnen worden gepersonaliseerd met de configuratieknop rechtsboven van de lijsten. Personalisatie wordt voor elke gebruiker opgeslagen.

Met de kolommen **[!UICONTROL Last update]** en **[!UICONTROL Last update by]** kunt u weergeven wanneer de laatste update van uw journey’s is uitgevoerd en welke gebruiker deze heeft uitgevoerd.

![](../assets/journey74.png)

In de deelvensters voor gebeurtenissen, databronnen en actieconfiguratie geeft het veld **[!UICONTROL Used in]** het aantal journey’s weer dat deze bepaalde gebeurtenis, veldengroep of actie gebruikt. U kunt klikken op de knop **[!UICONTROL View journeys]** om de lijst met corresponderende journey’s weer te geven.

![](../assets/journey3bis.png)

In de verschillende lijsten kunt u standaardacties op elk element uitvoeren. U kunt bijvoorbeeld een item dupliceren of verwijderen.

![](../assets/journey4.png)

## Bladeren door Adobe Experience Platform-velden {#friendly-names-display}

Bij het definiëren van een [gebeurtenispayload](../event/defining-the-payload-fields.md), een [veldengroep-payload](../datasource/field-groups.md) en het selecteren van velden in de [expressie-editor](../expression/expressionadvanced.md) wordt naast de veldnaam ook de weergavenaam weergegeven. Deze informatie wordt opgehaald uit de schemadefinitie in het Gegevenservaringmodel.

Als er beschrijvingen als xdm:alternateDisplayInfo worden opgegeven tijdens het instellen van schema’s, worden de weergavenamen vervangen door de gebruikersvriendelijke namen. Dit is vooral handig wanneer u werkt met eVars en generieke velden. U kunt beschrijvende namen configureren via een API-aanroep. Zie de [ontwikkelaarshandleiding voor schemaregistratie](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) voor meer informatie.

![](../assets/xdm-from-descriptors.png)

Als een beschrijvende naam beschikbaar is, wordt het veld weergegeven als `<friendly-name>(<name>)`. Als er geen beschrijvende naam beschikbaar is, wordt de weergavenaam weergegeven, bijvoorbeeld `<display-name>(<name>)`. Als geen van deze waarden is gedefinieerd, wordt alleen de technische naam van het veld weergegeven: `<name>`.

>[!NOTE]
>
>De beschrijvende namen worden niet opgehaald wanneer u velden selecteert uit een samenvoeging van schema’s.

## Toegankelijkheid{#accessibility}

De toegankelijkheidsfuncties in Adobe Journey Optimizer worden geleverd door Adobe Experience Platform:

* Toegankelijkheid toetsenbord
* Kleurcontrast
* Validatie van vereiste velden

[Meer informatie](https://experienceleague.adobe.com/docs/experience-platform/accessibility/features.html){target=&quot;_blank&quot;} in Adobe Experience Platform-documentatie.

U kunt de volgende algemene sneltoetsen gebruiken in Adobe Journey Optimizer:

| Actie | Sneltoets |
| --- | --- |
| Tussen gebruikersinterface-elementen, -secties en -menugroepen verplaatsen | Tabtoets |
| Ga achterwaarts tussen gebruikersinterface-elementen, -secties en -menuproepen | Shift + Tab |
| Binnen secties verplaatsen om focus in te stellen op afzonderlijke elementen | Pijl |
| Een element dat de focus heeft selecteren of wissen | Enter of spatiebalk |
| Een selectie annuleren, een deelvenster samenvouwen of een dialoogvenster sluiten | Esc |

[Meer informatie](https://experienceleague.adobe.com/docs/experience-platform/accessibility/custom.html){target=&quot;_blank&quot;} in Adobe Experience Platform-documentatie.

U kunt deze sneltoetsen gebruiken in specifieke delen van Journey Optimizer:

<table>
  <thead>
    <tr>
      <th>Interface-element</th>
      <th>Actie</th>
      <th>Sneltoets</th>
    </tr>
  </thead>
  <tr>
    <td>Lijst met reizen, handelingen, gegevensbronnen of gebeurtenissen</td>
    <td>Een reis, handeling, gegevensbron of gebeurtenis maken</td>
    <td>C</td>
  </tr>
  <tr>
    <td rowspan="3">Reis canvas in conceptstatus</td>
    <td>Voeg een activiteit van het linkerpalet bij de eerste beschikbare positie toe, van boven tot onder</td>
    <td>Dubbelklik op de activiteit</td>
  </tr>
  <tr>
    <td>Alle activiteiten selecteren</td>
    <td>Ctrl + A (Windows)<br/>Command + A (Mac)</td>
  </tr>
  <tr>
    <td>Geselecteerde activiteiten verwijderen</td>
    <td>Verwijder of Backspace en ga vervolgens in om de verwijdering te bevestigen</td>
  </tr>
  <tr>
  <td rowspan="3">

Configuratievenster van deze elementen:

<ul>
  <li>Activiteit in een reis</li>
  <li>Gebeurtenis</li>
  <li>Gegevensbron</li>
  <li>Actie</li>
</ul>

</td>
    <td>Ga naar het volgende veld dat moet worden geconfigureerd</td>
    <td>Tabtoets</td>
  </tr>
  <tr>
    <td>Wijzigingen opslaan en het configuratievenster sluiten</td>
    <td>Enter</td>
  </tr>
  <tr>
    <td>Wijzigingen negeren en het configuratievenster sluiten</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td rowspan="4">Reizen in testmodus</td>
    <td>De testmodus in- of uitschakelen</td>
    <td>T</td>
  </tr>
  <tr>
    <td>Een gebeurtenis activeren tijdens een op een gebeurtenis gebaseerde reis</td>
    <td>E</td>
  </tr>
  <tr>
    <td>

Een gebeurtenis activeren in een op segmenten gebaseerde reis waarvoor de **[!UICONTROL Single profile at a time]** optie is ingeschakeld

</td>
    <td>P</td>
  </tr>
  <tr>
    <td>De testlogboeken weergeven</td>
    <td>L</td>
  </tr>
<!-- //Ajouter ce raccourci quand il marchera (actuellement, le raccourci Ctrl/Cmd+F du navigateur a priorité sur celui de AJO).//
  <tr>
    <td>Page with a search bar</td>
    <td>Select the search bar</td>
    <td>Ctrl/Command + F</td>
  </tr>
-->
  <tr>
    <td>Tekstveld</td>
    <td>Alle tekst in het geselecteerde veld selecteren</td>
    <td>Ctrl + A (Windows)<br/>Command + A (Mac)</td>
  </tr>
  <tr>
    <td rowspan="2">Pop-upvenster</td>
    <td>Wijzigingen opslaan of de handeling bevestigen</td>
    <td>Enter</td>
  </tr>
  <tr>
    <td>Sluit het venster</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td>Eenvoudige expressie-editor</td>
    <td>Een veld selecteren en toevoegen</td>
    <td>Dubbelklikken op een veld</td>
  </tr>
  <tr>
    <td>Bladeren door XDM-velden</td>
    <td>Alle velden van een knooppunt selecteren</td>
    <td>Het bovenliggende knooppunt selecteren</td>
  </tr>
  <tr>
    <td>Payloadvoorbeeld</td>
    <td>Selecteer de lading</td>
    <td>Ctrl + A (Windows)<br/>Command + A (Mac)</td>
  </tr>
</table>
