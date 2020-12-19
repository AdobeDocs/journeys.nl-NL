---
product: adobe campaign
solution: Journey Orchestration
title: Payloadvelden definiëren
description: Meer informatie over het definiëren van laadvelden
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 6%

---


# Payloadvelden definiëren {#concept_yrw_3qt_52b}

De ladingsdefinitie staat u toe om de informatie te kiezen het systeem van de gebeurtenis in uw reis verwacht te ontvangen en de sleutel om te identificeren welke persoon aan de gebeurtenis wordt geassocieerd. De nuttige lading is gebaseerd op de Experience Cloud XDM gebiedsdefinitie. Raadpleeg [deze pagina](https://docs.adobe.com/content/help/nl-NL/experience-platform/xdm/home.html) voor meer informatie over XDM.

1. Selecteer een XDM-schema in de lijst en klik op het veld **[!UICONTROL Payload]** of op het pictogram **[!UICONTROL Edit]**.

   ![](../assets/journey8.png)

   Alle velden die in het schema zijn gedefinieerd, worden weergegeven. De lijst met velden verschilt per schema. U kunt naar een specifiek veld zoeken of de filters gebruiken om alle knooppunten en velden of alleen de geselecteerde velden weer te geven. Volgens de schemadefinitie zijn sommige velden mogelijk verplicht en vooraf geselecteerd. U kunt de selectie niet opheffen.

   >[!NOTE]
   >
   >Controleer of u de mix &quot;orkest&quot; aan het XDM-schema hebt toegevoegd. Dit zal ervoor zorgen dat uw schema alle vereiste informatie bevat om met [!DNL Journey Orchestration] te werken.

   ![](../assets/journey9.png)

1. Selecteer de velden die u van de gebeurtenis wilt ontvangen. Dit zijn de gebieden die de bedrijfsgebruiker in de reis zal hefboomwerking hebben. Zij moeten ook de sleutel omvatten die zal worden gebruikt om de persoon te identificeren verbonden aan de gebeurtenis (zie [deze pagina](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Voor door het systeem gegenereerde gebeurtenissen wordt het veld **[!UICONTROL eventID]** automatisch toegevoegd aan de lijst met geselecteerde velden, zodat [!DNL Journey Orchestration] de gebeurtenis kan identificeren. Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. Zie [deze pagina](../event/previewing-the-payload.md).

1. Wanneer u klaar bent met het selecteren van de benodigde velden, klikt u op **[!UICONTROL Save]** of drukt u op **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   Het aantal geselecteerde velden wordt weergegeven in het veld **[!UICONTROL Payload]**.

   ![](../assets/journey12.png)
