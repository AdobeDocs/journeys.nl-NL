---
title: De reis maken
description: Leer hoe u de eenvoudige gebruiksrechtovereenkomst maakt
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
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---


# De reis maken{#concept_eyw_mcy_w2b}

De **bedrijfsgebruiker** kan nu de reis bouwen. Onze reis zal slechts één weg met de volgende activiteiten omvatten:

* het &quot;SpaBeacon&quot; **[!UICONTROL Event]**: wanneer een persoon in de buurt van het spa - baken loopt , zal het systeem een evenement ontvangen en zal de reis voor die persoon beginnen .
* een **[!UICONTROL Condition]** activiteit om na te gaan of de persoon een vrouw is
* een **[!UICONTROL Email]** activiteit (met Adobe Campaign Standard)
* an **[!UICONTROL End]** activity

>[!NOTE]
>
>De **[!UICONTROL Push]** en **[!UICONTROL Email]** activiteiten zijn alleen beschikbaar in het palet als u Adobe Campaign Standard hebt.

Raadpleeg [](../building-journeys/journey.md)voor meer informatie over het maken van een reis.

1. Klik in het bovenste menu op het **[!UICONTROL Home]** tabblad en **[!UICONTROL Create]** maak een nieuwe rit.

   ![](../assets/journey31.png)

1. Bewerk de eigenschappen van de rit in het configuratievenster dat aan de rechterkant wordt weergegeven. We noemen het &#39;Spa-reis&#39; en stellen het in op een maand, van 1 tot en met 31 december.

   ![](../assets/journeyuc1_8.png)

1. Begin uw reis te ontwerpen door de &quot;SpaBeacon&quot;-gebeurtenis van het palet naar het canvas te slepen. U kunt ook dubbelklikken op de gebeurtenis in het palet om deze aan het canvas toe te voegen.

   ![](../assets/journeyuc1_9.png)

1. Laten we nu een voorwaarde toevoegen om te controleren of de persoon een vrouw is. Sleep een voorwaardenactiviteit naar uw reis.

   ![](../assets/journeyuc1_10.png)

1. Kies het **[!UICONTROL Data Source Condition]** type en klik in het **[!UICONTROL Expression]** veld. U kunt ook een voorwaardelabel definiëren dat wordt weergegeven op de pijl, in het canvas.

   ![](../assets/journeyuc1_11.png)

1. Zoek met de eenvoudige expressie-editor naar het genderveld (_persoon > geslacht_) en zet dit naar rechts om de volgende voorwaarde te maken: &quot;geslacht is gelijk aan &quot;vrouw&quot;.

   ![](../assets/journeyuc1_12.png)

1. Zet een **[!UICONTROL Email]** activiteit neer en selecteer uw transactiemalplaatje van de &quot;korting van de Buur&quot;transactie. Deze sjabloon is ontworpen met Adobe Campaign. Zie deze [pagina](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

   ![](../assets/journeyuc1_13.png)

1. Klik in het **[!UICONTROL Email]** veld en selecteer het e-mailadres in de gegevensbron.

   ![](../assets/journeyuc1_14.png)

1. Definieer op dezelfde manier de velden voor voornaam en achternaam aanpassen van de gegevensbron.

   ![](../assets/journeyuc1_15.png)

1. Zet een **[!UICONTROL End]** activiteit neer.

   ![](../assets/journeyuc1_17.png)

1. Klik op de **[!UICONTROL Test]** knevel en test uw reis gebruikend testprofielen. Als er een fout optreedt, deactiveert u de testmodus, wijzigt u de reis en test u deze opnieuw. Raadpleeg voor meer informatie over de testmodus [](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. Wanneer de test overtuigend is, kunt u uw reis van het hoogste juiste drop-down menu publiceren.

   ![](../assets/journeyuc1_18.png)

De volgende keer dat een vrouw in de buurt van het baken loopt, ontvangt ze meteen een persoonlijke e-mail met de titel &quot;Spa-korting&quot;.
