---
product: adobe campaign
title: Databronnen configureren
description: Leer hoe te om de gegevensbron voor de reis geavanceerde gebruiksgeval te vormen
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 15%

---

# Databronnen configureren {#concept_vml_hdy_w2b}

In ons gebruiksgeval, willen wij verpersoonlijkingsgegevens voor onze berichten gebruiken. We moeten ook controleren of de persoon een loyaliteitslid is en in de afgelopen 24 uur niet is benaderd. Deze informatie wordt opgeslagen in het gegevensbestand van het Profiel van de Klant in real time. De **technisch gebruiker** moet de Adobe Experience Platform-gegevensbron configureren om deze velden op te halen.

Voor extra informatie over gegevensbronconfiguratie, verwijs naar [deze pagina](../datasource/about-data-sources.md).

1. Selecteer in het menuvenster de optie **[!UICONTROL Admin]**. In de **[!UICONTROL Data sources]** sectie, klikt u op **[!UICONTROL Manage]**.
1. Selecteer de ingebouwde Adobe Experience Platform-gegevensbron.

   ![](../assets/journey23.png)

1. Controleer in de vooraf geconfigureerde groepsvelden of de volgende velden zijn geselecteerd:

   * _person > name > firstName_
   * _person > name > lastName_
   * _PersonalEmail > address_

1. Klikken **[!UICONTROL Add a New Field Group]** selecteert u een **[!UICONTROL Profiles]** en voeg het schema toe **Loyalty** veld voor onze conditie. De **Loyalty** field is a custom field and was added in XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Klikken **[!UICONTROL Add a New Field Group]** selecteert u een **[!UICONTROL ExperienceEvent]** schema en kies de gebieden nodig voor onze voorwaarde op het aantal berichten die in een bepaalde periode worden verzonden: _tijdstempel_ voor de datum en _directMarketing > send > value_ voor het aantal verzonden berichten.

   ![](../assets/journeyuc2_7.png)

1. Klik op **[!UICONTROL Save]**.

We moeten ook controleren of de persoon een boeking heeft in het hotelreserveringssysteem. De **technisch gebruiker** moet een tweede gegevensbron configureren om dit veld op te halen.

1. Klik in de lijst met gegevensbronnen op **[!UICONTROL Add]** om een nieuwe externe gegevensbron toe te voegen om de verbinding aan uw systeem van de hotelreserve te bepalen.

   ![](../assets/journeyuc2_9.png)

1. Voer bijvoorbeeld een naam in voor uw gegevensbron en de URL van de externe service: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >We raden u uit beveiligingsoverwegingen sterk aan om HTTPS te gebruiken.

1. Configureer de verificatie volgens de configuratie van de externe service: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** of **[!UICONTROL API key]**. In ons voorbeeld, kiezen wij &quot;Basis&quot;voor het type en specificeren de gebruikersbenaming en het wachtwoord voor de API vraag.

   ![](../assets/journeyuc2_10.png)

1. Klikken **[!UICONTROL Add a New Field Group]** om de op te halen informatie en de API-parameters te definiëren. Voor ons voorbeeld is er slechts één parameter (de id), dus moeten we één veldgroep maken met de volgende informatie:

   * **[!UICONTROL Method]**: selecteer de methode POST of GET. In ons geval selecteren we de methode GET.
   * **[!UICONTROL Response Payload]**: klik binnen **[!UICONTROL Payload]** veld en plak een voorbeeld van de laadbewerking. Controleer of de veldtypen correct zijn. Telkens wanneer de API wordt aangeroepen, haalt het systeem alle velden op die in het payloadvoorbeeld zijn opgenomen. In ons voorbeeld bevat de lading alleen de reserveringsstatus:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: Voer de parameter in die overeenkomt met de sleutel die wordt gebruikt om elke klant te identificeren, &#39;id&#39; in ons voorbeeld. De waarde van deze parameter zal in de reis worden bepaald.

   ![](../assets/journeyuc2_11.png)

1. Klik op **[!UICONTROL Save]**.

   De gegevensbronnen zijn nu gevormd en klaar om in uw reis worden gebruikt.
