---
title: De laadvelden definiëren
description: Meer informatie over het definiëren van laadvelden
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

---


# De laadvelden definiëren {#concept_yrw_3qt_52b}

De ladingsdefinitie staat u toe om de informatie te kiezen het systeem van de gebeurtenis in uw reis verwacht te ontvangen en de sleutel om te identificeren welke persoon aan de gebeurtenis wordt geassocieerd. De payload is gebaseerd op de XDM-velddefinitie van Experience Cloud. Raadpleeg deze [pagina](https://www.adobe.io/apis/cloudplatform/dataservices/xdm.html)voor meer informatie over XDM.

1. Selecteer een XDM-schema in de lijst en klik op het **[!UICONTROL Payload]**veld of op het**[!UICONTROL Edit]** pictogram.

   ![](../assets/journey8.png)

   Alle velden die in het schema zijn gedefinieerd, worden weergegeven. De lijst met velden verschilt per schema. U kunt naar een specifiek veld zoeken of de filters gebruiken om alle knooppunten en velden of alleen de geselecteerde velden weer te geven. Volgens de schemadefinitie zijn sommige velden mogelijk verplicht en vooraf geselecteerd. U kunt de selectie niet opheffen.

   >[!NOTE]
   >
   >Controleer of u de mix &quot;orkest&quot; aan het XDM-schema hebt toegevoegd. Dit zal ervoor zorgen dat uw schema alle vereiste informatie bevat om met de Orchestratie van de Reis te werken.

   ![](../assets/journey9.png)

1. Selecteer de velden die u van de gebeurtenis wilt ontvangen. Dit zijn de gebieden die de bedrijfsgebruiker in de reis zal hefboomwerking hebben. Zij moeten ook de sleutel omvatten die zal worden gebruikt om de persoon te identificeren verbonden aan de gebeurtenis (zie [](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Het **[!UICONTROL eventID]**veld wordt automatisch toegevoegd aan de lijst met geselecteerde velden, zodat Journey Orchestration de gebeurtenis kan identificeren. Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. Zie[](../event/previewing-the-payload.md).

1. Klik **[!UICONTROL Save]**of druk op**[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   Het aantal geselecteerde velden wordt weergegeven in het **[!UICONTROL Payload]**veld.

   ![](../assets/journey12.png)
