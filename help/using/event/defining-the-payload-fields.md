---
product: adobe campaign
title: Payloadvelden definiëren
description: Meer informatie over het definiëren van laadvelden
feature: Journeys
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 3%

---

# Payloadvelden definiëren {#concept_yrw_3qt_52b}



>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


De ladingsdefinitie staat u toe om de informatie te kiezen het systeem van de gebeurtenis in uw reis verwacht te ontvangen en de sleutel om te identificeren welke persoon aan de gebeurtenis wordt geassocieerd. De nuttige lading is gebaseerd op de Experience Cloud XDM gebiedsdefinitie. Voor meer informatie over XDM, verwijs naar [ deze pagina ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=nl).

1. Selecteer een XDM-schema in de lijst en klik op het veld **[!UICONTROL Payload]** of op het pictogram **[!UICONTROL Edit]** .

   ![](../assets/journey8.png)

   Alle velden die in het schema zijn gedefinieerd, worden weergegeven. De lijst met velden verschilt per schema. U kunt naar een specifiek veld zoeken of de filters gebruiken om alle knooppunten en velden of alleen de geselecteerde velden weer te geven. Volgens de schemadefinitie zijn sommige velden mogelijk verplicht en vooraf geselecteerd. U kunt de selectie niet opheffen. Alle velden die verplicht zijn voor een juiste ontvangst van de gebeurtenis door Journey Orchestration, zijn standaard geselecteerd.

   >[!NOTE]
   >
   >Controleer of u de mix &quot;orkest&quot; aan het XDM-schema hebt toegevoegd. Zo zorgt u ervoor dat het schema alle vereiste gegevens bevat om met [!DNL Journey Orchestration] te werken.

   ![](../assets/journey9.png)

1. Selecteer de velden die u van de gebeurtenis wilt ontvangen. Dit zijn de gebieden die de bedrijfsgebruiker in de reis zal hefboomwerking hebben. Zij moeten ook de sleutel omvatten die zal worden gebruikt om de persoon te identificeren verbonden aan de gebeurtenis (zie [ deze pagina ](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Voor door het systeem gegenereerde gebeurtenissen wordt het veld **[!UICONTROL eventID]** automatisch toegevoegd aan de lijst met geselecteerde velden, zodat [!DNL Journey Orchestration] de gebeurtenis kan identificeren. Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. Zie [deze pagina](../event/previewing-the-payload.md).

1. Klik op **[!UICONTROL Save]** of druk op **[!UICONTROL Enter]** wanneer u klaar bent met het selecteren van de benodigde velden.

   ![](../assets/journey11.png)

   Het aantal geselecteerde velden wordt weergegeven in het veld **[!UICONTROL Payload]** .

   ![](../assets/journey12.png)
