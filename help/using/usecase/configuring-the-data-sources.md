---
title: De gegevensbronnen configureren
description: Leer hoe te om de gegevensbron voor de reis geavanceerde gebruiksgeval te vormen
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---


# De gegevensbronnen configureren {#concept_vml_hdy_w2b}

In ons gebruiksgeval, willen wij verpersoonlijkingsgegevens voor onze berichten gebruiken. We moeten ook controleren of de persoon een loyaliteitslid is en in de afgelopen 24 uur niet is benaderd. Deze informatie wordt opgeslagen in het gegevensbestand van het Profiel van de Klant in real time. De **technische gebruiker** moet de gegevensbron van het Adobe Experience Platform vormen om die gebieden terug te winnen.

Voor extra informatie over gegevensbronconfiguratie, verwijs naar [](../datasource/about-data-sources.md).

1. Klik in het bovenste menu op het **[!UICONTROL Data Sources]** tabblad en selecteer de gegevensbron van het ingebouwde Adobe Experience Platform.

   ![](../assets/journey23.png)

1. Controleer in de vooraf geconfigureerde groepsvelden of de volgende velden zijn geselecteerd:

   * _person > name > firstName_
   * _person > name > lastName_
   * _PersonalEmail > address_

1. Klik **[!UICONTROL Add a New Field Group]**, selecteer een **[!UICONTROL Profiles]** schema en voeg het gebied van het Lid **van de** Loyalty voor onze voorwaarde toe. Het veld **Loyalty-lid** is een aangepast veld en is toegevoegd in XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Klik **[!UICONTROL Add a New Field Group]**, selecteer een **[!UICONTROL ExperienceEvent]** schema en kies de gebieden nodig voor onze voorwaarde op het aantal berichten die in een bepaalde periode worden verzonden: _timestamp_ voor de datum en _directMarketing > verzendt > waarde_ voor het aantal verzonden berichten.

   ![](../assets/journeyuc2_7.png)

1. Klik op **[!UICONTROL Save]**.

We moeten ook controleren of de persoon een boeking heeft in het hotelreserveringssysteem. De **technische gebruiker** moet een tweede gegevensbron vormen om dit gebied terug te winnen.

1. In de lijst van gegevensbronnen, klik **[!UICONTROL Add]** om een nieuwe externe gegevensbron toe te voegen om de verbinding aan uw systeem van de hotelreserve te bepalen.

   ![](../assets/journeyuc2_9.png)

1. Voer bijvoorbeeld een naam in voor uw gegevensbron en de URL van de externe service: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >We raden u ten zeerste aan HTTPS te gebruiken om beveiligingsredenen.

1. Vorm de authentificatie afhankelijk van de externe de dienstconfiguratie: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** of **[!UICONTROL API key]**. In ons voorbeeld, kiezen wij &quot;Basis&quot;voor het type en specificeren de gebruikersbenaming en het wachtwoord voor de API vraag.

   ![](../assets/journeyuc2_10.png)

1. Klik **[!UICONTROL Add a New Field Group]** om de op te halen informatie en de API-parameters te definiëren. Voor ons voorbeeld is er slechts één parameter (de id), dus moeten we één veldgroep maken met de volgende informatie:

   * **[!UICONTROL Method]**: Selecteer de methode POST of GET. In ons geval selecteren we de methode GET.
   * **[!UICONTROL Cache duration]**: dit varieert afhankelijk van de frequentie van de API-aanroepen. In ons geval wordt het reserveringssysteem elke 10 minuten bijgewerkt.
   * **[!UICONTROL Response Payload]**: Klik in het **[!UICONTROL Payload]** veld en plak een voorbeeld van de laadbewerking. Controleer of de veldtypen correct zijn. Telkens wanneer de API wordt aangeroepen, haalt het systeem alle velden op die in het payload-voorbeeld zijn opgenomen. In ons voorbeeld bevat de lading alleen de reserveringsstatus:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: Voer de parameter in die overeenkomt met de sleutel die wordt gebruikt om elke klant te identificeren, &#39;id&#39; in ons voorbeeld. De waarde van deze parameter zal in de reis worden bepaald.

   ![](../assets/journeyuc2_11.png)

1. Klik op **[!UICONTROL Save]**.

   De gegevensbronnen zijn nu gevormd en klaar om in uw reis worden gebruikt.
