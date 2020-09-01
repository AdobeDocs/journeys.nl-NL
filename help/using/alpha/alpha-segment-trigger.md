---
title: Segmentactiviteit lezen
description: Meer informatie over de activiteit Leessegment.
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
source-git-commit: 967f453145dcf9af0e3efc5d52854d0c5c68c54f
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---


# Segmentactiviteit lezen {#segment-trigger-activity}

## Informatie over de activiteit Leessegment {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>Als er op het canvas tijdens de publicatie of tijdens de activering van de testmodus een Adobe Campaign Standard-actie buiten de doos aanwezig is, wordt de rit vertraagd bij 13 ingangen per seconde. Anders zal de reis worden vertraagd bij 1000 gebeurtenissen per seconde.

Met de activiteit Leessegment kunt u alle personen die tot een Adobe Experience Platform-segment behoren een reis laten maken. Het betreden van een reis kan één keer of op regelmatige basis plaatsvinden.

Laten we zeggen dat je een Gold-klantensegment hebt op Adobe Experience Platform. Met de activiteit van het Leessegment, kunt u alle individuen van het Gouden klantensegment een reis maken en hen tot geïndividualiseerde reizen maken die alle reisfunctionaliteit gebruiken: voorwaarden, timers, gebeurtenissen, handelingen.

## De activiteit configureren {#configuring-segment-trigger-activity}

>[!NOTE]
>
>Vanwege de vertraging bij de segmentuitvoer is het niet mogelijk om een op segmenten gebaseerde reis binnen een kortere periode dan 1 uur te activeren.

1. Ontvouw de **[!UICONTROL Orchestration]** categorie en laat een **[!UICONTROL Read Segment]** activiteit op uw canvas vallen.

   De activiteit moet als eerste stap van een reis worden geplaatst.

1. Voeg een **[!UICONTROL Label]** aan de activiteit (facultatief) toe.

1. Kies in het **[!UICONTROL Segment]** veld het Adobe Experience Platform-segment dat de rit moet ingaan en klik op **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >U kunt de kolommen in de lijst aanpassen en sorteren.

   ![](../assets/segment-trigger-segment-selection.png)

   Zodra het segment wordt toegevoegd, staat de **[!UICONTROL Copy]** knoop u toe om zijn naam en identiteitskaart te kopiëren:

   `{"name":"Gold customers,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-trigger-copy.png)

1. Kies in het **[!UICONTROL Namespace]** veld de naamruimte die u wilt gebruiken om de personen te identificeren. For more on namespaces, refer to [this section](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Personen die behoren tot een segment dat niet de geselecteerde identiteit (naamruimte) onder hun verschillende identiteiten heeft, kunnen de reis niet betreden.

1. De **[!UICONTROL Read Segment]** activiteit staat u toe om de tijd te specificeren waarop het segment de reis zal ingaan. Om dit te doen, klik de **[!UICONTROL Edit journey schedule]** verbinding om tot de eigenschappen van de reis toegang te hebben, dan vorm het **[!UICONTROL Scheduler type]** gebied.

   ![](../assets/segment-trigger-schedule.png)

   Standaard komen segmenten de reis binnen, **[!UICONTROL As soon as possible]** dat wil zeggen 1 uur nadat de reis is gepubliceerd. Als u wilt dat het segment de reis op een specifieke datum/tijd of op een terugkomende basis ingaat, selecteer de gewenste waarde van de lijst.

   >[!NOTE]
   >
   >De **[!UICONTROL Schedule]** sectie is alleen beschikbaar wanneer een **[!UICONTROL Read Segment]** activiteit op het canvas is neergezet.

   ![](../assets/segment-trigger-properties.png)

## Testen en publiceren van de reis {#testing-publishing}

Met deze **[!UICONTROL Read Segment]** activiteit kunt u de reis testen op een uniform profiel of op 100 willekeurig gekozen testprofielen uit de profielen die voor het segment in aanmerking komen.

Hiervoor activeert u de testmodus en selecteert u de gewenste optie in het linkerdeelvenster.

![](../assets/segment-trigger-test-modes.png)

U kunt de testwijze dan vormen zoals gebruikelijk. Gedetailleerde stappen voor het testen van een reis worden in [dit gedeelte](../building-journeys/testing-the-journey.md)beschreven.

Houd er rekening mee dat u door het testen van de reis met maximaal 100 profielen tegelijk de voortgang van de individuele personen op de reis niet kunt bijhouden met behulp van de visuele stroom.

Zodra de tests succesvol zijn, kunt u uw reis publiceren (zie het [Publiceren van de reis](../building-journeys/publishing-the-journey.md)). Personen die tot het segment behoren, komen de reis binnen op de datum/tijd die in de **[!UICONTROL Scheduler]** afdeling Eigenschappen van de reis is vermeld.

>[!IMPORTANT]
>
>Onthoud dat Adobe Experience Platform-segmenten één keer per dag (**batchsegmenten** ) of in realtime (**gestreamde** segmenten) worden berekend.
>
>Als het geselecteerde segment wordt gestreamd, zullen de individuen die tot dit segment behoren potentieel de reis in real time ingaan. Als het segment partij is, zullen de mensen die nieuw voor dit segment worden gekwalificeerd de reis potentieel ingaan wanneer de segmentberekening op Adobe Experience Platform wordt uitgevoerd.
