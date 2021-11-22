---
product: adobe campaign
title: Journey samenstellen
description: Leer hoe u de eenvoudige gebruiksrechtovereenkomst maakt
feature: Journeys
role: User
level: Intermediate
exl-id: 22bcd7f4-03ee-4e4c-b221-9f14aeadded6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 36%

---

# Journey samenstellen{#concept_eyw_mcy_w2b}

De **bedrijfsgebruiker** kan nu de journey bouwen. Onze reis zal slechts één weg met de volgende activiteiten omvatten:

* de &quot;SpaBeacon&quot; **[!UICONTROL Event]**: wanneer een persoon in de buurt van het spa - baken loopt , zal het systeem een evenement ontvangen en zal de reis voor die persoon beginnen .
* a **[!UICONTROL Condition]** activiteit om na te gaan of de persoon een vrouw is
* een **[!UICONTROL Email]** activiteit (met Adobe Campaign Standard)
* een **[!UICONTROL End]** activiteit

>[!NOTE]
>
>De **[!UICONTROL Push]**- en **[!UICONTROL Email]**-activiteiten zijn alleen beschikbaar in het palet als u Adobe Campaign Standard hebt.

Voor meer informatie over hoe u een reis kunt maken, raadpleegt u [deze pagina](../building-journeys/journey.md).

1. Klik in het bovenste menu op de tabbladen **[!UICONTROL Home]** en **[!UICONTROL Create]** om een nieuwe journey te maken.

   ![](../assets/journey31.png)

1. Bewerk de eigenschappen van de journey in het configuratievenster dat aan de rechterkant wordt weergegeven. We noemen het &#39;Spa-reis&#39; en stellen het in op een maand, van 1 tot en met 31 december.

   ![](../assets/journeyuc1_8.png)

1. Begin uw reis te ontwerpen door de &quot;SpaBeacon&quot;-gebeurtenis van het palet naar het canvas te slepen. U kunt ook dubbelklikken op de gebeurtenis in het palet om deze aan het canvas toe te voegen.

   ![](../assets/journeyuc1_9.png)

1. Laten we nu een voorwaarde toevoegen om te controleren of de persoon een vrouw is. Sleep een voorwaardeactiviteit en zet deze neer in uw journey.

   ![](../assets/journeyuc1_10.png)

1. Kies het type **[!UICONTROL Data Source Condition]** en klik in het veld **[!UICONTROL Expression]**. U kunt ook een voorwaardelabel definiëren die wordt weergegeven op de pijl, in het canvas.

   ![](../assets/journeyuc1_11.png)

1. Zoek met de eenvoudige expressie-editor naar het genderveld (_persoon > geslacht_) en zet deze naar rechts om de volgende voorwaarde te maken: &quot;geslacht is gelijk aan &quot;vrouw&quot;.

   ![](../assets/journeyuc1_12.png)

1. Een dropknop **[!UICONTROL Email]** en selecteer je transactiesjabloon voor &quot;Spa-korting&quot;. Deze sjabloon is ontworpen met Adobe Campaign. Zie dit [page](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=nl).

   ![](../assets/journeyuc1_13.png)

1. Klik in het dialoogvenster **[!UICONTROL Email]** en selecteer het e-mailadres in de gegevensbron.

   ![](../assets/journeyuc1_14.png)

1. Definieer op dezelfde manier de velden voor voornaam en achternaam aanpassen van de gegevensbron.

   ![](../assets/journeyuc1_15.png)

1. Een dropknop **[!UICONTROL End]** activiteit.

   ![](../assets/journeyuc1_17.png)

1. Klik op de knop **[!UICONTROL Test]** en test uw reis met testprofielen. Als er een fout optreedt, deactiveert u de testmodus, wijzigt u de journey en test u deze opnieuw. Raadpleeg voor meer informatie over de testmodus [deze pagina](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. Wanneer de test is geslaagd is, kunt u uw journey vanuit het vervolgkeuzemenu rechtsboven publiceren.

   ![](../assets/journeyuc1_18.png)

De volgende keer dat een vrouw in de buurt van het baken loopt, ontvangt ze meteen een persoonlijke e-mail met de titel &quot;Spa-korting&quot;.
