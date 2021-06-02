---
product: adobe campaign
title: Hefboomwerking van vermoeidheidsscores
description: Leer hoe u vermoeidheidsscores tijdens reizen kunt gebruiken
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 9%

---


# Journey-AI gebruiken {#concept_dsh_1ry_wfb}

Met deze gebruiksaanwijzing kunt u de vermoeidheidsscores benutten om te voorkomen dat uw klanten op reis te veel vragen.

>[!NOTE]
>
>De functie voor voorspellende vermoeidheidsscore is alleen beschikbaar voor klanten die de [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html) gebruiken.

## De gebeurtenis configureren {#section_ptb_ws1_ffb}

Voer de stappen uit die worden beschreven in [deze pagina](../event/about-events.md).

## De databron configureren {#section_o3n_4yy_wfb}

Voer de volgende stappen uit om de gebieden van de vermoeidheidsscore in de ingebouwde gegevensbron te selecteren:

1. Klik in het bovenste menu op het tabblad **[!UICONTROL Data Sources]** en selecteer de Adobe Experience Platform-gegevensbron voor de build-in.

   ![](../assets/journey23.png)

1. Controleer of de velden die nodig zijn voor het gebruik van hoofdletters en kleine letters zijn geselecteerd.
1. Klik op **[!UICONTROL Add a New Field Group]**, selecteer het **[!UICONTROL Profiles]**-model en voeg de velden **[!UICONTROL fatigueLevel]** en **[!UICONTROL fatigueScore]** toe (onder _tripAI > emailScore > moeheid_).

   ![](../assets/journeyuc3_1.png)

1. Klik op **[!UICONTROL Save]**.

## De journey samenstellen {#section_uzm_pyy_wfb}

Als u de reis wilt maken, valideren en publiceren, voert u de stappen uit die worden beschreven in [deze pagina](../building-journeys/journey.md).

In ons gebruiksgeval gebruiken we het veld **[!UICONTROL fatigueLevel]**. U kunt ook het veld **[!UICONTROL fatigueScore]** gebruiken.

Voer de volgende stappen uit om het vermoeidheidsniveau tijdens uw reis te benutten:

1. Voeg een gebeurtenis en een voorwaarde in uw reis toe.

   ![](../assets/journeyuc2_14.png)

1. Kies het type **[!UICONTROL Data Source Condition]** en klik in het veld **[!UICONTROL Expression]**. 

   ![](../assets/journeyuc3_2.png)

1. Zoek met de eenvoudige expressie-editor naar het veld **[!UICONTROL fatigueLevel]** (_ExperiencePlatformDataSource > JourneyAIScores > Profile > tripAI > emailScore > vermoeidheid_), zet het naar rechts en maak de volgende voorwaarde: &quot;fatigueLevel is gelijk aan &quot;Low&quot;. Klik op **[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   De geavanceerde expressie is:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. In de voorwaarde, creeer twee andere wegen voor middelgrote en hoge vermoeiingsniveaus.

   ![](../assets/journeyuc3_4.png)

1. U kunt nu verschillende acties toevoegen voor elk vermoeidheidsniveau.

   ![](../assets/journeyuc3_5.png)
