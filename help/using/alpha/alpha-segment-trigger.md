---
title: Segmenttriggeractiviteit
description: Meer informatie over Segment Trigger
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
source-git-commit: b66cdb31b62b4627ff7378e48879ffadfedda5cb
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---


# Segmenttriggeractiviteit {#segment-trigger-activity}

## Informatie over de activiteit Segmenttrigger {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>Als er op het canvas tijdens de publicatie of tijdens de activering van de testmodus een Adobe Campaign Standard-actie buiten de doos aanwezig is, wordt de rit vertraagd bij 13 ingangen per seconde. <br>Als er op het canvas geen buiten-de-box-activiteit van Adobe Campaign Standard aanwezig is tijdens de publicatie of activering van de testmodus, wordt de rit vertraagd bij 1000 gebeurtenissen per seconde.

Met de Segment Trigger-activiteit kunt u alle personen die tot een Adobe Experience Platform-segment behoren een reis laten maken. Het betreden van een reis kan één keer of op regelmatige basis plaatsvinden.

Laten we zeggen dat je een Gold-klantensegment hebt op Adobe Experience Platform. Met de Segment Trigger-activiteit, kunt u alle individuen die tot het Gouden klantensegment behoren een reis maken en hen tot geïndividualiseerde reizen maken die alle reisfunctionaliteit gebruiken: voorwaarden, timers, gebeurtenissen, handelingen.

## De activiteit configureren {#configuring-segment-trigger-activity}

>[!NOTE]
>
>Vanwege de vertraging bij de segmentuitvoer is het niet mogelijk om een op segmenten gebaseerde reis binnen een kortere periode dan 1 uur te activeren.

1. Ontvouw de **[!UICONTROL Orchestration]** categorie en laat een **[!UICONTROL Segment Trigger]** activiteit op uw canvas vallen.

   De activiteit moet als eerste stap van een reis worden geplaatst.

1. Configureer de activiteit **[!UICONTROL Scheduler type]**.

   Door gebrek, zal het segment de reis ingaan **[!UICONTROL As soon as possible]**, die 1 uur betekent na de reis wordt gepubliceerd. Als u wilt dat het segment de reis op een specifieke datum/tijd of op een terugkomende basis ingaat, selecteer de gewenste optie van de lijst.

   Bij terugkerende ritten kunt u ook het begin en het einde van de rit definiëren.

   ![](../assets/segment-trigger-schedule.png)

1. Kies in het **[!UICONTROL Segment]** veld het Adobe Experience Platform-segment dat de rit moet ingaan en klik op **[!UICONTROL Save]**.

   ![](../assets/segment-trigger-segment-selection.png)

1. Kies in het **[!UICONTROL Namespace]** veld de naamruimte die u wilt gebruiken om de personen te identificeren. For more on namespaces, refer to [this section](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Personen die behoren tot een segment dat niet de geselecteerde identiteit (naamruimte) onder hun verschillende identiteiten heeft, kunnen de reis niet betreden.

1. Klik **[!UICONTROL Ok]** om te bevestigen. U kunt dan beschikbare activiteiten gebruiken om uw reis te bouwen.

1. Zodra de reis klaar is, kunt u het potentieel testen (zie het [Testen van de reis](../building-journeys/testing-the-journey.md)).

   Wanneer de testmodus wordt geactiveerd op een rit die begint met een **[!UICONTROL Segment Trigger]** activiteit, worden 100 testprofielen willekeurig gekozen uit de profielen die voor het geselecteerde segment in aanmerking komen. De testlogboeken zullen u toestaan om de weg van individuen in de reis en potentiële aangetroffen fouten te zien (zie het [Bekijken van de logboeken](../building-journeys/testing-the-journey.md#viewing_logs)).

   >[!NOTE]
   >
   >U zult de 100 personen na de reis niet kunnen zien met behulp van het visuele debietkenmerk dat bestaat bij eenheidstreizen.

1. U kunt uw reis dan publiceren (zie het [Publiceren van de reis](../building-journeys/publishing-the-journey.md)). De personen die tot het segment behoren zullen de reis op de datum/de tijd ingaan die in de de activiteitenplanner van de Trekker van het Segment wordt gespecificeerd.

   >[!IMPORTANT]
   >
   >Onthoud dat Adobe Experience Platform-segmenten één keer per dag (**batchsegmenten** ) of in realtime (**gestreamde** segmenten) worden berekend.
   >
   >Als het geselecteerde segment wordt gestreamd, zullen de individuen die tot dit segment behoren potentieel de reis in real time ingaan. Als het segment partij is, zullen de mensen die nieuw voor dit segment worden gekwalificeerd de reis potentieel ingaan wanneer de segmentberekening op Adobe Experience Platform wordt uitgevoerd.
