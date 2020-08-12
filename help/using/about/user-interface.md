---
title: De gebruikersinterface
description: Meer informatie over de gebruikersinterface
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 3c6c20feb2d461a5780dde5539811beee2eb78b7
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 89%

---


# Gebruikersinterface{#concept_rcq_lqt_52b}

>[!NOTE]
>
>We raden u aan Chrome als uw internetbrowser te gebruiken om het beste uit [!DNL Journey Orchestration] te halen. De interface wordt weergegeven in de taal die is gedefinieerd in IMS. Als uw IMS-taal niet door [!DNL Journey Orchestration] wordt ondersteund, wordt de interface weergegeven in het Engels.
>
>Deze documentatie wordt regelmatig aangepast aan recente wijzigingen in het product. Sommige screenshots kunnen echter iets afwijken van de interface van het product.

## Toegang tot [!DNL Journey Orchestration]{#accessing_journey_orchestration}

Voor toegang tot de [!DNL Journey Orchestration]-interface klikt u op het pictogram **[!UICONTROL App Selector]** rechtsboven. Then click **[!UICONTROL Journey Orchestration]**, on the right side, below **[!UICONTROL Experience Platform]**.

![](../assets/journey1.png)

U kunt [!DNL Journey Orchestration] ook openen via de startpagina van Experience Cloud, in de sectie **[!UICONTROL Quick access]**.

![](../assets/journey1bis.png)

## De interface verkennen{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="Journeylijst"
>abstract="Met de journeylijst kunt u al uw journey’s tegelijk weergeven, hun status bekijken en basisacties uitvoeren. U kunt uw journey’s dupliceren, stopzetten of verwijderen. Afhankelijk van de journey zijn bepaalde acties mogelijk niet beschikbaar. U kunt bijvoorbeeld een gesloten journey niet verwijderen of opnieuw starten. U kunt deze dupliceren of een nieuwe versie maken op basis van de gesloten journey. U kunt ook de zoekbalk gebruiken om een journey te zoeken."
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="Demovideo bekijken"

Met de bovenste menu’s kunt u navigeren door de verschillende functies van [!DNL Journey Orchestration]: **[!UICONTROL Home]** (de journey’s), **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** en **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Klik op het pictogram ![](../assets/icon-context.png) in de rechterbovenhoek van het scherm om de contextafhankelijke Help weer te geven. Deze is beschikbaar in de verschillende [!DNL Journey Orchestration]-lijstschermen (journey’s, gebeurtenissen, acties en databronnen). Hiermee kunt u een korte beschrijving weergeven van de huidige functionaliteit en toegang krijgen tot verwante artikelen en video’s.

![](../assets/journey2bis.png)

## Zoeken en filteren{#section_lgm_hpz_pgb}

In de lijsten **[!UICONTROL Home]**,**[!UICONTROL Data Sources]**, **[!UICONTROL Events]** en **[!UICONTROL Actions]** kunt u met een zoekbalk naar een item zoeken.

U kunt het dialoogvenster **[!UICONTROL Filters]** openen door te klikken op het filterpictogram linksboven van de lijst. Met het menu Filters kunt u de weergegeven elementen filteren op basis van verschillende criteria. U kunt ervoor kiezen alleen de elementen van een bepaald type of een bepaalde status weer te geven, de elementen die u hebt gemaakt, of de elementen die in de afgelopen 30 dagen zijn gewijzigd.

In the **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** and **[!UICONTROL Actions]** lists, use the **[!UICONTROL Creation filters]** to filter on the creation date and user. U kunt bijvoorbeeld besluiten alleen gebeurtenissen weer te geven die u in de afgelopen 30 dagen hebt gemaakt.

In de journeylijst (onder **[!UICONTROL Home]**) kunt u, naast **[!UICONTROL Creation filters]**, ook de weergegeven journey’s filteren op basis van hun status en versie (**[!UICONTROL Status and version filters]**). U kunt er ook voor kiezen om alleen de journey’s weer te geven die een bepaalde gebeurtenis, veldengroep of actie (**[!UICONTROL Activity filters]** en **[!UICONTROL Data filters]**) gebruiken. Met **[!UICONTROL Publication filters]** kunt u een publicatiedatum of gebruiker selecteren. U kunt er bijvoorbeeld voor kiezen om alleen de nieuwste versies van live journey’s weer te geven die gisteren zijn gepubliceerd. Zie [](../building-journeys/using-the-journey-designer.md).

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

Als er beschrijvingen als xdm:alternateDisplayInfo worden opgegeven tijdens het instellen van schema’s, worden de weergavenamen vervangen door de gebruikersvriendelijke namen. Dit is vooral handig wanneer u werkt met eVars en generieke velden. U kunt beschrijvende namen configureren via een API-aanroep. Zie de [ontwikkelaarshandleiding voor schemaregistratie](https://docs.adobe.com/content/help/nl-NL/experience-platform/xdm/api/getting-started.html) voor meer informatie.

![](../assets/xdm-from-descriptors.png)

Als een beschrijvende naam beschikbaar is, wordt het veld weergegeven als `<friendly-name>(<name>)`. Als er geen beschrijvende naam beschikbaar is, wordt de weergavenaam weergegeven, bijvoorbeeld `<display-name>(<name>)`. Als geen van deze waarden is gedefinieerd, wordt alleen de technische naam van het veld weergegeven: `<name>`.

>[!NOTE]
>
>De beschrijvende namen worden niet opgehaald wanneer u velden selecteert uit een samenvoeging van schema’s.

## De verschillende sneltoetsen gebruiken{#section_ksq_zr1_ffb}

Hier volgt een overzicht van de verschillende sneltoetsen die beschikbaar zijn in de interface van [!DNL Journey Orchestration].

_In de lijst van journey’s, acties, databronnen of gebeurtenissen:_

* Druk op **c** om een nieuwe journey, actie, databron of gebeurtenis te maken.

_Bij het configureren van een activiteit in een journey:_

Het canvas wordt automatisch opgeslagen. U kunt linksboven op het canvas de opslagstatus zien.

* Druk op **Escape** om het configuratievenster te sluiten en de aangebrachte wijzigingen te negeren. Dit is het equivalent van de knop **[!UICONTROL Cancel]**.
* Press **Enter** or click outside the pane to close the configuration pane. Wijzigingen worden opgeslagen. Dit is het equivalent van de knop **[!UICONTROL Ok]**.
* If you press **Delete** or **backspace**, you can then press **Enter** to confirm the deletion.

_In pop-ups:_

* Press **escape** to close it (equivalent of the **[!UICONTROL Cancel]** button).
* Press **Enter** to save or confirm (equivalent of the **[!UICONTROL Ok]** or **[!UICONTROL Save]** button).

_In het configuratiedeelvenster van de gebeurtenis, databron of actie:_

* Druk op **Escape** om het configuratievenster te sluiten zonder het op te slaan.
* Press **Enter** to save modifications and close the configuration pane.
* Druk op **Tab** om van het ene te configureren veld naar het andere te gaan.

_In de editor voor eenvoudige expressies_

* Dubbelklik op een veld aan de linkerkant om een query toe te voegen (equivalent van slepen en neerzetten).

_Wanneer u door XDM-velden bladert:_

* Als u een node inschakelt, worden alle velden van de node geselecteerd.

_In alle tekstgebieden:_

* Selecteer de tekst met de toetsencombinatie **Ctrl/Command + A**. In de payloadvoorvertoning wordt de payload geselecteerd.

_In een scherm met een zoekbalk:_

* Selecteer de zoekbalk met de toetsencombinatie **Ctrl/Command + F**.

_Op het canvas van een journey:_

* Gebruik de toetsencombinatie **Ctrl/Command + A** om alle activiteiten te selecteren.
* When one or several activities are selected, press **Delete** or **backspace** to delete them. Then you can press **Enter** to confirm in the confirmation pop-up.
* Dubbelklik op een activiteit in het linkerpalet om deze toe te voegen op de eerste beschikbare positie (van boven naar beneden).
