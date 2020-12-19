---
product: adobe campaign
solution: Journey Orchestration
title: Databronnen configureren
description: Leer hoe te om de gegevensbron voor de reis geavanceerde gebruiksgeval te vormen
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 14%

---


# Databronnen configureren {#concept_vml_hdy_w2b}

In ons gebruiksgeval, willen wij verpersoonlijkingsgegevens voor onze berichten gebruiken. We moeten ook controleren of de persoon een loyaliteitslid is en in de afgelopen 24 uur niet is benaderd. Deze informatie wordt opgeslagen in het gegevensbestand van het Profiel van de Klant in real time. De **technische gebruiker** moet de gegevensbron van Adobe Experience Platform vormen om die gebieden terug te winnen.

Voor extra informatie over gegevensbronconfiguratie, verwijs naar [deze pagina](../datasource/about-data-sources.md).

1. Klik in het bovenste menu op het tabblad **[!UICONTROL Data Sources]** en selecteer de Adobe Experience Platform-gegevensbron voor de build-in.

   ![](../assets/journey23.png)

1. Controleer in de vooraf geconfigureerde groepsvelden of de volgende velden zijn geselecteerd:

   * _person > name > firstName_
   * _person > name > lastName_
   * _PersonalEmail > address_

1. Klik **[!UICONTROL Add a New Field Group]**, selecteer een **[!UICONTROL Profiles]** schema en voeg **Loyalty lid** gebied voor onze voorwaarde toe. Het veld **Loyalty member** is een aangepast veld en is toegevoegd in XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Klik **[!UICONTROL Add a New Field Group]**, selecteer een **[!UICONTROL ExperienceEvent]** schema en kies de gebieden nodig voor onze voorwaarde op het aantal berichten die in een bepaalde periode worden verzonden: _timestamp_ voor de datum en _directMarketing > send > value_ voor het aantal verzonden berichten.

   ![](../assets/journeyuc2_7.png)

1. Klik op **[!UICONTROL Save]**.

We moeten ook controleren of de persoon een boeking heeft in het hotelreserveringssysteem. De **technische gebruiker** moet een tweede gegevensbron vormen om dit gebied terug te winnen.

1. In de lijst van gegevensbronnen, klik **[!UICONTROL Add]** om een nieuwe externe gegevensbron toe te voegen om de verbinding aan uw systeem van de hotelreserve te bepalen.

   ![](../assets/journeyuc2_9.png)

1. Voer bijvoorbeeld een naam in voor uw gegevensbron en de URL van de externe service: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >We raden u uit beveiligingsoverwegingen sterk aan om HTTPS te gebruiken.

1. Configureer de verificatie volgens de configuratie van de externe service: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** of **[!UICONTROL API key]**. In ons voorbeeld, kiezen wij &quot;Basis&quot;voor het type en specificeren de gebruikersbenaming en het wachtwoord voor de API vraag.

   ![](../assets/journeyuc2_10.png)

1. Klik op **[!UICONTROL Add a New Field Group]** om de informatie op te halen en de API-parameters te definiëren. Voor ons voorbeeld is er slechts één parameter (de id), dus moeten we één veldgroep maken met de volgende informatie:

   * **[!UICONTROL Method]**: selecteer de methode POST of GET. In ons geval selecteren we de methode GET.
   * **[!UICONTROL Cache duration]**: dit varieert afhankelijk van de frequentie van de API-aanroepen. In ons geval wordt het reserveringssysteem elke 10 minuten bijgewerkt.
   * **[!UICONTROL Response Payload]**: Klik in het  **[!UICONTROL Payload]** veld en plak een voorbeeld van de laadbewerking. Controleer of de veldtypen correct zijn. Telkens wanneer de API wordt aangeroepen, haalt het systeem alle velden op die in het payloadvoorbeeld zijn opgenomen. In ons voorbeeld bevat de lading alleen de reserveringsstatus:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: Voer de parameter in die overeenkomt met de sleutel die wordt gebruikt om elke klant te identificeren, &#39;id&#39; in ons voorbeeld. De waarde van deze parameter zal in de reis worden bepaald.

   ![](../assets/journeyuc2_11.png)

1. Klik op **[!UICONTROL Save]**.

   De gegevensbronnen zijn nu gevormd en klaar om in uw reis worden gebruikt.
