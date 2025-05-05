---
product: adobe campaign
title: Hefboomwerking van vermoeidheidsscores
description: Leer hoe u vermoeidheidsscores tijdens reizen kunt gebruiken
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 9%

---


# Journey-AI gebruiken {#concept_dsh_1ry_wfb}

Met deze gebruiksaanwijzing kunt u de vermoeidheidsscores benutten om te voorkomen dat uw klanten op reis te veel vragen.

>[!NOTE]
>
>De functie voor voorspellende vermoeidheidsscore is alleen beschikbaar voor klanten die de functie [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html?lang=nl-NL).

## De gebeurtenis configureren {#section_ptb_ws1_ffb}

Voer de in [deze pagina](../event/about-events.md).

## De databron configureren {#section_o3n_4yy_wfb}

Voer de volgende stappen uit om de gebieden van de vermoeidheidsscore in de ingebouwde gegevensbron te selecteren:

1. Selecteer in het menuvenster de optie **[!UICONTROL Admin]**. In de **[!UICONTROL Data sources]** sectie, klikt u op **[!UICONTROL Manage]**.
1. Selecteer de ingebouwde Adobe Experience Platform-gegevensbron.

   ![](../assets/journey23.png)

1. Controleer of de velden die nodig zijn voor het gebruik van hoofdletters en kleine letters zijn geselecteerd.
1. Klikken **[!UICONTROL Add a New Field Group]**, selecteert u de **[!UICONTROL Profiles]** model en voeg de **[!UICONTROL fatigueLevel]** en **[!UICONTROL fatigueScore]** velden (onder _tripAI > emailScore > vermoeidheid_).

   ![](../assets/journeyuc3_1.png)

1. Klik op **[!UICONTROL Save]**.

## Journey samenstellen {#section_uzm_pyy_wfb}

Volg de in [deze pagina](../building-journeys/journey.md).

In ons gebruiksgeval gebruiken we de **[!UICONTROL fatigueLevel]** veld. U kunt ook de opdracht **[!UICONTROL fatigueScore]** veld.

Voer de volgende stappen uit om het vermoeidheidsniveau tijdens uw reis te benutten:

1. Voeg een gebeurtenis en een voorwaarde in uw reis toe.

   ![](../assets/journeyuc2_14.png)

1. Kies het type **[!UICONTROL Data Source Condition]** en klik in het veld **[!UICONTROL Expression]**. 

   ![](../assets/journeyuc3_2.png)

1. Gebruikend de eenvoudige uitdrukkingsredacteur, zoek naar **[!UICONTROL fatigueLevel]** field (_ExperiencePlatformDataSource > JourneyAIScores > Profile > tripAI > emailScore > vermoeidheid_), zet het neer aan het recht en creeer de volgende voorwaarde: &quot;fatigueLevel is gelijk aan &quot;Low&quot;. Klik op **[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   De geavanceerde expressie is:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. In de voorwaarde, creeer twee andere wegen voor middelgrote en hoge vermoeiingsniveaus.

   ![](../assets/journeyuc3_4.png)

1. U kunt nu verschillende acties toevoegen voor elk vermoeidheidsniveau.

   ![](../assets/journeyuc3_5.png)
