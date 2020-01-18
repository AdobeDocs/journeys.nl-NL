---
title: Veldgroepen
description: Meer informatie over veldgroepen
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---



# Veldgroepen {#concept_ntl_ypt_52b}

## Veldgroepen definiëren {#section_dsz_kjd_fjb}

Voor elke gegevensbron kunt u verschillende veldgroepen definiëren, elk met een specifieke cacheduur. Hiermee kunt u de velden kiezen die u wilt ophalen uit de gegevensbron die u tijdens uw reizen wilt gebruiken.

U kunt bijvoorbeeld een veldgroep maken met het telefoonnummer, de e-mail, de voornaam en het adres van het profiel. Dan kunt u deze gegevens gebruiken om voorwaarden te creëren. U kunt bijvoorbeeld alleen een SMS-bericht verzenden als het telefoonnummer van het profiel niet leeg is. Als het leeg is, kunt u een e-mail verzenden.

Hoewel automatisch een standaardnaam wordt toegevoegd, raden wij u aan een naam aan uw veldgroep toe te voegen. De naam van de veldgroep is namelijk zichtbaar voor andere gebruikers in Journey Orchestration. U kunt het beste veldgroepen een relevante naam geven.

Wanneer een gegevensbrongebied in een reis wordt gebruikt, zal het systeem alle gebieden terugwinnen die voor die gebiedsgroep worden bepaald. Daarom is het verstandig alleen de velden te selecteren die u nodig hebt voor uw reizen. Hierdoor wordt de wachttijd bij het aanvragen van uw reizen verminderd, waardoor de prestaties toenemen. U kunt later gemakkelijk meer velden in veldgroepen toevoegen.

**[!UICONTROL Cache duration]**is ook belangrijk omdat dit u helpt de prestaties te optimaliseren. De duur van het geheime voorgeheugen betekent dat in een reis, als de gegevens van een gebiedsgroep eens worden teruggewonnen, het systeem het dan tijdelijk zal in het voorgeheugen onderbrengen. Als de zelfde gegevens later in de zelfde reis worden vereist, zal het systeem niet een ander verzoek aan de gegevensbron indienen. De configuratie van de geheim voorgeheugenduur zou voor elk gebruiksgeval moeten worden aangepast. Als u gegevens in real time zoals de status van de hotelreserve, weerinformatie of het aantal loyaliteitspunten moet terugwinnen, zult u de gebiedsgroep associëren die deze gebieden met een korte geheim voorgeheugenduur (1 seconde, bijvoorbeeld) bevat. Voor velden die minder vaak worden bijgewerkt (naam, geslacht), maakt u een tweede veldgroep met een langere cache (bijvoorbeeld 5 dagen).

Het aantal ritten dat een veldgroep gebruikt, wordt in het **[!UICONTROL Used in]**veld weergegeven. U kunt op de**[!UICONTROL View journeys]** knop klikken om de lijst met reizen weer te geven met deze veldgroep.

>[!NOTE]
>
>Als een veldgroep geen veld heeft, wordt deze niet weergegeven in de expressie-editor.

![](../assets/journey3bis.png)

## Levenscyclus veldgroep {#section_abk_njd_fjb}

U kunt velden toevoegen aan of verwijderen uit een veldgroep die niet wordt gebruikt in concepten of live reizen.

U kunt een veld toevoegen, maar u kunt dit niet verwijderen uit een veldgroep die wordt gebruikt in een of meer concepten of livedagen. Zo voorkomt u dat de reis wordt onderbroken.

Voer de volgende stappen uit om een veld te verwijderen uit een veldgroep die wordt gebruikt voor een of meer reizen. Laten we een voorbeeld gebruiken van een veldgroep met de naam &quot;Veldgroep A&quot;.

1. Plaats de cursor in de lijst met veldgroepen op &quot;Veldgroep A&quot; en klik op het **[!UICONTROL Duplicate]**pictogram aan de rechterkant. Geef de gedupliceerde veldgroep bijvoorbeeld de naam &quot;Veldgroep B&quot;.
1. Verwijder in &quot;Veldgroep B&quot; de velden die u niet meer wilt gebruiken.
1. Controleer in &quot;Veldgroep A&quot; waar deze veldgroep wordt gebruikt. Deze informatie wordt weergegeven in het **[!UICONTROL Used in]**veld.
1. Open alle reizen die gebruikmaken van &quot;Veldgroep A&quot;.
1. Maak nieuwe versies van elk van deze reizen. Bewerk alle activiteiten met &quot;Veldgroep A&quot; en selecteer &quot;Veldgroep B&quot;.
1. Oude versies van ritten met &quot;Veldgroep A&quot; stoppen. U zou dan geen reis moeten hebben gebruikend &quot;Groep A van het Gebied&quot;.
1. Verwijder &quot;Veldgroep A&quot; zoals deze niet meer wordt gebruikt.
