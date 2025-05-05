---
product: adobe campaign
title: Databronnen configureren
description: Leer hoe te om de gegevensbron voor de reis geavanceerde gebruiksgeval te vormen
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 12%

---

# Databronnen configureren {#concept_vml_hdy_w2b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


In ons gebruiksgeval, willen wij verpersoonlijkingsgegevens voor onze berichten gebruiken. We moeten ook controleren of de persoon een loyaliteitslid is en in de afgelopen 24 uur niet is benaderd. Deze informatie wordt opgeslagen in het gegevensbestand van het Profiel van de Klant in real time. De **technische gebruiker** moet de gegevensbron van Adobe Experience Platform vormen om die gebieden terug te winnen.

Voor extra informatie over gegevensbronconfiguratie, verwijs naar [ deze pagina ](../datasource/about-data-sources.md).

1. Selecteer **[!UICONTROL Admin]** in het menuvenster. Klik in de sectie **[!UICONTROL Data sources]** op **[!UICONTROL Manage]** .
1. Selecteer de ingebouwde Adobe Experience Platform-gegevensbron.

   ![](../assets/journey23.png)

1. Controleer in de vooraf geconfigureerde groepsvelden of de volgende velden zijn geselecteerd:

   * _persoon > naam > firstName_
   * _persoon > naam > lastName_
   * _PersonalEmail > adres_

1. Klik **[!UICONTROL Add a New Field Group]**, selecteer een **[!UICONTROL Profiles]** schema en voeg het **lid van de Loyalty** gebied voor onze voorwaarde toe. Het **gebied van het lid van de Loyalty** is een douanegebied en werd toegevoegd in XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Klik **[!UICONTROL Add a New Field Group]**, selecteer een **[!UICONTROL ExperienceEvent]** schema en kies de gebieden nodig voor onze voorwaarde op het aantal berichten die in een bepaalde periode worden verzonden: _timestamp_ voor de datum en _directMarketing > verzendt > waarde_ voor het aantal verzonden berichten.

   ![](../assets/journeyuc2_7.png)

1. Klik op **[!UICONTROL Save]**.

We moeten ook controleren of de persoon een boeking heeft in het hotelreserveringssysteem. De **technische gebruiker** moet een tweede gegevensbron vormen om dit gebied terug te winnen.

1. Klik in de lijst met gegevensbronnen op **[!UICONTROL Add]** om een nieuwe externe gegevensbron toe te voegen om de verbinding met uw hotelreserveringssysteem te definiëren.

   ![](../assets/journeyuc2_9.png)

1. Ga een naam voor uw gegevensbron en URL van de externe dienst in, bijvoorbeeld: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >We raden u ten zeerste aan HTTPS te gebruiken om beveiligingsredenen.

1. Configureer de verificatie volgens de configuratie van de externe service: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** of **[!UICONTROL API key]**. In ons voorbeeld, kiezen wij &quot;Basis&quot;voor het type en specificeren de gebruikersbenaming en het wachtwoord voor de API vraag.

   ![](../assets/journeyuc2_10.png)

1. Klik op **[!UICONTROL Add a New Field Group]** om de informatie op te halen en de API-parameters te definiëren. Voor ons voorbeeld is er slechts één parameter (de id), dus moeten we één veldgroep maken met de volgende informatie:

   * **[!UICONTROL Method]**: selecteer de methode POST of GET. In ons geval selecteren we de methode GET.
   * **[!UICONTROL Response Payload]** : klik in het veld **[!UICONTROL Payload]** en plak een voorbeeld van de laadbewerking. Controleer of de veldtypen correct zijn. Telkens wanneer de API wordt aangeroepen, haalt het systeem alle velden op die in het payloadvoorbeeld zijn opgenomen. In ons voorbeeld bevat de lading alleen de reserveringsstatus:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: voer de parameter in die overeenkomt met de sleutel die wordt gebruikt om elke klant te identificeren, &#39;id&#39; in ons voorbeeld. De waarde van deze parameter zal in de reis worden bepaald.

   ![](../assets/journeyuc2_11.png)

1. Klik op **[!UICONTROL Save]**.

   De gegevensbronnen zijn nu gevormd en klaar om in uw reis worden gebruikt.
