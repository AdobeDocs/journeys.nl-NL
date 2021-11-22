---
product: adobe campaign
title: Payloadvelden definiëren
description: Meer informatie over het definiëren van laadvelden
feature: Journeys
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 5%

---

# Payloadvelden definiëren {#concept_yrw_3qt_52b}

De ladingsdefinitie staat u toe om de informatie te kiezen het systeem van de gebeurtenis in uw reis verwacht te ontvangen en de sleutel om te identificeren welke persoon aan de gebeurtenis wordt geassocieerd. De nuttige lading is gebaseerd op de Experience Cloud XDM gebiedsdefinitie. Voor meer informatie over XDM, verwijs naar [deze pagina](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=nl).

1. Selecteer een XDM-schema in de lijst en klik op de knop **[!UICONTROL Payload]** of op **[!UICONTROL Edit]** pictogram.

   ![](../assets/journey8.png)

   Alle velden die in het schema zijn gedefinieerd, worden weergegeven. De lijst met velden verschilt per schema. U kunt naar een specifiek veld zoeken of de filters gebruiken om alle knooppunten en velden of alleen de geselecteerde velden weer te geven. Volgens de schemadefinitie zijn sommige velden mogelijk verplicht en vooraf geselecteerd. U kunt de selectie niet opheffen. Alle velden die verplicht zijn voor een juiste ontvangst van de gebeurtenis door Journey Orchestration worden standaard geselecteerd.

   >[!NOTE]
   >
   >Controleer of u de mix &quot;orkest&quot; aan het XDM-schema hebt toegevoegd. Dit zal ervoor zorgen dat uw schema alle vereiste informatie bevat om met te werken [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. Selecteer de velden die u van de gebeurtenis wilt ontvangen. Dit zijn de gebieden die de bedrijfsgebruiker in de reis zal hefboomwerking hebben. Ze moeten ook de sleutel bevatten die wordt gebruikt om de persoon te identificeren die aan de gebeurtenis is gekoppeld (zie [deze pagina](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Voor door het systeem gegenereerde gebeurtenissen wordt de **[!UICONTROL eventID]** wordt automatisch toegevoegd aan de lijst met geselecteerde velden, zodat [!DNL Journey Orchestration] kan de gebeurtenis identificeren. Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. Zie [deze pagina](../event/previewing-the-payload.md).

1. Als u de gewenste velden hebt geselecteerd, klikt u op **[!UICONTROL Save]** of drukken **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   Het aantal geselecteerde velden wordt weergegeven in het dialoogvenster **[!UICONTROL Payload]** veld.

   ![](../assets/journey12.png)
