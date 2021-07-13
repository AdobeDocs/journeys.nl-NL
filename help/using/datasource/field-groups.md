---
product: adobe campaign
title: Veldgroepen
description: Meer informatie over veldgroepen
feature: Journeys
role: User
level: Intermediate
exl-id: 6f7f2673-9080-4274-afa3-a0255798f78d
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 0%

---

# Veldgroepen {#concept_ntl_ypt_52b}

Veldgroepen zijn sets velden die u kunt ophalen van een gegevensbron en gebruiken tijdens een reis.

## Veldgroepen definiëren {#section_dsz_kjd_fjb}

Voor elke gegevensbron kunt u verschillende veldgroepen definiëren, elk met een specifieke cacheduur.

U kunt bijvoorbeeld een veldgroep maken met het telefoonnummer, de e-mail, de voornaam en het adres van het profiel. Dan kunt u deze gegevens gebruiken om voorwaarden te creëren. U kunt bijvoorbeeld alleen een SMS-bericht verzenden als het telefoonnummer van het profiel niet leeg is. Als het leeg is, kunt u een e-mail verzenden.

Hoewel automatisch een standaardnaam wordt toegevoegd, raden wij u aan een naam aan uw veldgroep toe te voegen. De naam van de veldgroep is namelijk zichtbaar voor andere gebruikers in [!DNL Journey Orchestration]. U kunt het beste veldgroepen een relevante naam geven.

Wanneer een gegevensbrongebied in een reis wordt gebruikt, zal het systeem alle gebieden terugwinnen die voor die gebiedsgroep worden bepaald. Daarom is het verstandig alleen de velden te selecteren die u nodig hebt voor uw reizen. Hierdoor wordt de wachttijd bij het aanvragen van uw reizen verminderd, waardoor de prestaties toenemen. U kunt later gemakkelijk meer velden in veldgroepen toevoegen.

**[!UICONTROL Cache duration]** is ook belangrijk omdat dit u helpt de prestaties te optimaliseren. De duur van het geheime voorgeheugen betekent dat in een reis, als de gegevens van een gebiedsgroep eens worden teruggewonnen, het systeem het dan tijdelijk zal in het voorgeheugen onderbrengen. Als de zelfde gegevens later in de zelfde reis worden vereist, zal het systeem niet een ander verzoek aan de gegevensbron indienen. De configuratie van de geheim voorgeheugenduur zou voor elk gebruiksgeval moeten worden aangepast. Als u gegevens in real time zoals de status van de hotelreserve, weerinformatie of het aantal loyaliteitspunten moet terugwinnen, zult u de gebiedsgroep associëren die deze gebieden met een korte geheim voorgeheugenduur (1 seconde, bijvoorbeeld) bevat. Voor velden die minder vaak worden bijgewerkt (naam, geslacht), maakt u een tweede veldgroep met een langere cache (bijvoorbeeld 5 dagen).

Het aantal ritten dat een veldgroep gebruikt, wordt weergegeven in het veld **[!UICONTROL Used in]**. U kunt op de knop **[!UICONTROL View journeys]** klikken om de lijst met reizen weer te geven met deze veldgroep.

>[!NOTE]
>
>Als een veldgroep geen veld heeft, wordt deze niet weergegeven in de expressie-editor.

![](../assets/journey3bis.png)

## Levenscyclus veldgroep {#section_abk_njd_fjb}

U kunt velden toevoegen aan of verwijderen uit een veldgroep die niet wordt gebruikt in concepten of live reizen.

U kunt een veld toevoegen, maar u kunt dit niet verwijderen uit een veldgroep die wordt gebruikt in een of meer concepten of livedagen. Zo voorkomt u dat de reis wordt onderbroken.

Voer de volgende stappen uit om een veld te verwijderen uit een veldgroep die wordt gebruikt voor een of meer reizen. Laten we een voorbeeld gebruiken van een veldgroep met de naam &quot;Veldgroep A&quot;.

1. Plaats de cursor in de lijst met veldgroepen op Veldgroep A en klik op het pictogram **[!UICONTROL Duplicate]** rechts. Geef de gedupliceerde veldgroep bijvoorbeeld de naam &quot;Veldgroep B&quot;.
1. Verwijder in &quot;Veldgroep B&quot; de velden die u niet meer wilt gebruiken.
1. Controleer in &quot;Veldgroep A&quot; waar deze veldgroep wordt gebruikt. Deze informatie wordt weergegeven in het veld **[!UICONTROL Used in]**.
1. Open alle reizen die gebruikmaken van &quot;Veldgroep A&quot;.
1. Maak nieuwe versies van elk van deze reizen. Bewerk alle activiteiten met &quot;Veldgroep A&quot; en selecteer &quot;Veldgroep B&quot;.
1. Oude versies van ritten met &quot;Veldgroep A&quot; stoppen. U zou dan geen reis moeten hebben gebruikend &quot;Groep A van het Gebied&quot;.
1. Verwijder &quot;Veldgroep A&quot; zoals deze niet meer wordt gebruikt.
